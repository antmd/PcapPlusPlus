cmake_minimum_required(VERSION 3.0)
project(PcapPlusPlus)

include(CMakePrintHelpers)

function(absolute_paths out_paths_var)
    cmake_parse_arguments(
        ap
        ""
        "BASE_DIR"
        "PATHS"
        ${ARGN}
    )

    # Make relative paths absolute (needed later on)
    set(abs_paths_list)

    if (NOT ap_BASE_DIR)
        set(ap_BASE_DIR ${CMAKE_CURRENT_SOURCE_DIR})
    endif()

    foreach (p ${ap_PATHS})
        if (NOT IS_ABSOLUTE "${p}")
            list(APPEND abs_paths_list "${ap_BASE_DIR}/${p}")
        else()
            list(APPEND abs_paths_list "${p}")
        endif()
    endforeach ()

    set(${out_paths_var} "${abs_paths_list}" PARENT_SCOPE)
endfunction()

function(add_sources _target)
    include(CMakeParseArguments)
    cmake_parse_arguments(
        "ts"
        ""
        "BASE_DIR;FILES_VAR"
        "INTERFACE;PUBLIC;PRIVATE"
        ${ARGN})

    if (NOT ts_BASE_DIR)
        set(ts_BASE_DIR ${CMAKE_CURRENT_LIST_DIR})
    endif()

    if (ts_INTERFACE) 
        absolute_paths(abs_paths BASE_DIR ${ts_BASE_DIR} PATHS ${ts_INTERFACE})
        target_sources(${_target} INTERFACE ${abs_paths})
    endif()
    if (ts_PUBLIC) 
        absolute_paths(abs_paths BASE_DIR ${ts_BASE_DIR} PATHS ${ts_PUBLIC})
        target_sources(${_target} PUBLIC ${abs_paths})
    endif()
    if (ts_PRIVATE) 
        absolute_paths(abs_paths BASE_DIR ${ts_BASE_DIR} PATHS ${ts_PRIVATE})
        target_sources(${_target} PRIVATE ${abs_paths})
    endif()

    if(ts_FILES_VAR)
        set(${ts_FILES_VAR} ${abs_paths} PARENT_SCOPE)
    endif()

endfunction()

if(CMAKE_HOST_APPLE)
    set(CommonDefines -DMACOS)
elseif(CMAKE_HOST_UNIX)
    set(CommonDefines -DLINUX)
endif()

set(ThirdPartyDir ${CMAKE_CURRENT_SOURCE_DIR}/3rdParty)
set(EndianPortableIncludeDir ${ThirdPartyDir}/EndianPortable/include)
set(LightPcapNgDir ${ThirdPartyDir}/LightPcapNg/LightPcapNg)
add_subdirectory(${LightPcapNgDir})
target_include_directories(light_pcapng_static PUBLIC ${LightPcapNgDir}/include)
target_include_directories(light_pcapng PUBLIC ${LightPcapNgDir}/include)

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib CACHE FILEPATH "Location for built libraries" FORCE)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib CACHE FILEPATH "Location for built libraries" FORCE)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin CACHE FILEPATH "Location for built executables" FORCE)

add_subdirectory(Common++)
add_subdirectory(Pcap++)
add_subdirectory(Packet++)
add_subdirectory(Examples)
