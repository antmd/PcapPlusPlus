add_executable(pcap_search
    main.cpp
    )


target_link_libraries(pcap_search
    PRIVATE
        pcappp
    )
