
add_library(commonpp STATIC)
target_include_directories(commonpp PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/header)
target_compile_definitions(commonpp PUBLIC ${CommonDefines})

if(CMAKE_HOST_APPLE)
    target_include_directories(commonpp PUBLIC /usr/include/malloc)
elseif(CMAKE_HOST_UNIX)
    target_include_directories(commonpp PUBLIC /usr/include/netinet)
endif()

include(header/CMakeLists.txt)
include(src/CMakeLists.txt)

install(TARGETS commonpp
    ARCHIVE DESTINATION lib
)
install(FILES ${CommonPPHeader} 
    DESTINATION ${CMAKE_INSTALL_PREFIX}/include/${CMAKE_PROJECT_NAME}
)
