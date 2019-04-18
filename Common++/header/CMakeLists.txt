set(CommonPPHeader
    GeneralUtils.h
    IpAddress.h
    IpUtils.h
    LRUList.h
    Logger.h
    MacAddress.h
    PcapPlusPlusVersion.h
    PlatformSpecificUtils.h
    PointerVector.h
    SystemUtils.h
    TablePrinter.h
    )

add_sources(commonpp BASEDIR ${CMAKE_CURRENT_LIST_DIR} PUBLIC ${CommonPPHeader})
