add_library(icmp_file_transfer_lib STATIC EXCLUDE_FROM_ALL
    Common.cpp
    Common.h
    )
target_link_libraries(icmp_file_transfer_lib 
    PUBLIC 
        PcapPlusPlus::Pcap
    )


add_executable(icmp_file_transfer_catcher EXCLUDE_FROM_ALL
    IcmpFileTransfer-catcher.cpp
    )


target_link_libraries(icmp_file_transfer_catcher
    PRIVATE
        icmp_file_transfer_lib
    )

add_executable(icmp_file_transfer_pitcher EXCLUDE_FROM_ALL
    IcmpFileTransfer-pitcher.cpp
    )


target_link_libraries(icmp_file_transfer_pitcher
    PRIVATE
        icmp_file_transfer_lib
    )

add_dependencies(examples icmp_file_transfer_pitcher)
add_dependencies(examples icmp_file_transfer_catcher)
