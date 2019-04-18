
add_library(pcappp STATIC)

target_include_directories(pcappp 
    PUBLIC 
        ${CMAKE_CURRENT_SOURCE_DIR}/header
    )

set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads MODULE REQUIRED)

target_link_libraries(pcappp 
    PUBLIC 
        packetpp
        -lpcap
        Threads::Threads
    )

include(header/CMakeLists.txt)
include(src/CMakeLists.txt)

install(TARGETS pcappp
    ARCHIVE DESTINATION lib
)
install(FILES ${PcapPPHeader} 
    DESTINATION ${CMAKE_INSTALL_PREFIX}/include/${CMAKE_PROJECT_NAME}
)
