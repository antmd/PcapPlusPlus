add_executable(http_analyzer EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(http_analyzer
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples http_analyzer)
