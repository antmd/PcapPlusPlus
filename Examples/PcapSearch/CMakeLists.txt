add_executable(pcap_search EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(pcap_search
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples pcap_search)
