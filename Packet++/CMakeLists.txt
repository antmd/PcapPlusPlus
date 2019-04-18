
add_library(packetpp STATIC)

target_include_directories(packetpp 
    PUBLIC 
        ${EndianPortableIncludeDir}
        ${CMAKE_CURRENT_SOURCE_DIR}/header
    )

target_link_libraries(packetpp 
    PUBLIC 
        commonpp
        light_pcapng_static
    )

include(header/CMakeLists.txt)
include(src/CMakeLists.txt)

install(TARGETS packetpp
    ARCHIVE DESTINATION lib
)
install(FILES ${PacketPPHeader} 
    DESTINATION ${CMAKE_INSTALL_PREFIX}/include/${CMAKE_PROJECT_NAME}
)
