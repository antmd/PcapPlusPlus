add_executable(ssl_analyzer EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(ssl_analyzer
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples ssl_analyzer)
