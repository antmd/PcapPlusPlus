
add_library(pcappp STATIC)
target_include_directories(pcappp PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/header)
target_link_libraries(pcappp PUBLIC packetpp)

include(header/CMakeLists.txt)
include(src/CMakeLists.txt)
