add_executable(benchmark EXCLUDE_FROM_ALL
    benchmark.cpp
    )


target_link_libraries(benchmark
    PRIVATE
        PcapPlusPlus::Pcap
    )

add_dependencies(examples benchmark)
