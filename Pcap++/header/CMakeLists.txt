set(PcapPPHeaderNames
    Device.h
    DpdkDevice.h
    DpdkDeviceList.h
    NetworkUtils.h
    PcapDevice.h
    PcapFileDevice.h
    PcapFilter.h
    PcapLiveDevice.h
    PcapLiveDeviceList.h
    PcapRemoteDevice.h
    PcapRemoteDeviceList.h
    PfRingDevice.h
    PfRingDeviceList.h
    RawSocketDevice.h
    WinPcapLiveDevice.h
    )

add_sources(pcappp 
    FILES_VAR PcapPPHeader
    BASEDIR ${CMAKE_CURRENT_LIST_DIR} 
    PUBLIC ${PcapPPHeaderNames}
    )
