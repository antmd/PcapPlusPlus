if(USE_PF_RING)

add_executable(pfring_filter_traffic EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(pfring_filter_traffic
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples pfring_filter_traffic)

endif(USE_PF_RING)
