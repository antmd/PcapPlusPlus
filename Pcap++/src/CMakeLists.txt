set(PcapPPSource
    DpdkDevice.cpp
    DpdkDeviceList.cpp
    NetworkUtils.cpp
    PcapDevice.cpp
    PcapFileDevice.cpp
    PcapFilter.cpp
    PcapLiveDevice.cpp
    PcapLiveDeviceList.cpp
    PcapRemoteDevice.cpp
    PcapRemoteDeviceList.cpp
    PfRingDevice.cpp
    PfRingDeviceList.cpp
    RawSocketDevice.cpp
    WinPcapLiveDevice.cpp
    )

add_sources(pcappp BASEDIR ${CMAKE_CURRENT_LIST_DIR} PUBLIC ${PcapPPSource})
