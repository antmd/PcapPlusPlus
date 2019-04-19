set(CommonPPSource
    GeneralUtils.cpp
    IpAddress.cpp
    IpUtils.cpp
    Logger.cpp
    MacAddress.cpp
    PcapPlusPlusVersion.cpp
    SystemUtils.cpp
    TablePrinter.cpp
    )

add_sources(commonpp BASEDIR ${CMAKE_CURRENT_LIST_DIR} PRIVATE ${CommonPPSource})
