add_executable(arping EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(arping
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples arp_spoofing)
