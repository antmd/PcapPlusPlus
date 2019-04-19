add_executable(ip_frag_util EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(ip_frag_util
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples ip_frag_util)
