add_executable(pcap_splitter EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(pcap_splitter
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples pcap_splitter)
