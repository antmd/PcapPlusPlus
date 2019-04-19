add_executable(ip_defrag_util EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(ip_defrag_util
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples ip_defrag_util)
