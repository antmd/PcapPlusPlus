
add_library(pcappp)
add_library(PcapPlusPlus::Pcap ALIAS pcappp)

target_include_directories(pcappp 
    PUBLIC 
        ${CMAKE_CURRENT_SOURCE_DIR}/header
    )

set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads MODULE REQUIRED)

target_link_libraries(pcappp 
    PUBLIC 
        PcapPlusPlus::Packet
        Threads::Threads
        -lpcap
    )

include(header/CMakeLists.txt)
include(src/CMakeLists.txt)

install(TARGETS pcappp
    ARCHIVE DESTINATION lib
)
install(FILES ${PcapPPHeader} 
    DESTINATION ${CMAKE_INSTALL_PREFIX}/include/${CMAKE_PROJECT_NAME}
)
