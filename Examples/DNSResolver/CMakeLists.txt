add_executable(dns_resolver EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(dns_resolver
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples dns_resolver)
