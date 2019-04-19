add_executable(dns_spoofing EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(dns_spoofing
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples dns_spoofing)
