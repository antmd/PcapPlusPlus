if (USE_DPDK)

add_executable(dpdk_bridge EXCLUDE_FROM_ALL
    main.cpp
    )


target_link_libraries(dpdk_bridge
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples dpdk_bridge)

endif(USE_DPDK)
