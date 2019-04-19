if (USE_DPDK)

add_executable(dpdk_filter_traffic EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(dpdk_filter_traffic
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples dpdk_filter_traffic)

endif (USE_DPDK)
