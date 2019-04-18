add_executable(pcap_printer EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(pcap_printer
    PRIVATE
        pcappp
    )
