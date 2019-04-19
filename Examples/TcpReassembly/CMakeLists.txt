add_executable(tcp_reassembly EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(tcp_reassembly
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples tcp_reassembly)
