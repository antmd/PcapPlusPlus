add_executable(arp_spoofing EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(arp_spoofing
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples arp_spoofing)
