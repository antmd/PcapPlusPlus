
set(ExampleDirs
    ArpSpoofing
    Arping
    DNSResolver
    DnsSpoofing
    DpdkBridge
    DpdkExample-FilterTraffic
    HttpAnalyzer
    IPDefragUtil
    IPFragUtil
    IcmpFileTransfer
    PcapPlusPlus-benchmark
    PcapPrinter
    PcapSearch
    PcapSplitter
    PfRingExample-FilterTraffic
    SSLAnalyzer
    TcpReassembly
    )

add_custom_target(examples)

foreach(ExampleDir ${ExampleDirs})
    add_subdirectory(${ExampleDir})
endforeach()

