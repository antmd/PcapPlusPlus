set(PacketPPHeaderNames
    ArpLayer.h
    DhcpLayer.h
    DnsLayer.h
    DnsLayerEnums.h
    DnsResource.h
    DnsResourceData.h
    EthLayer.h
    GreLayer.h
    HttpLayer.h
    IPReassembly.h
    IPv4Layer.h
    IPv6Extensions.h
    IPv6Layer.h
    IcmpLayer.h
    IgmpLayer.h
    Layer.h
    MplsLayer.h
    NullLoopbackLayer.h
    PPPoELayer.h
    Packet.h
    PacketTrailerLayer.h
    PacketUtils.h
    PayloadLayer.h
    ProtocolType.h
    RadiusLayer.h
    RawPacket.h
    SSLCommon.h
    SSLHandshake.h
    SSLLayer.h
    SdpLayer.h
    SipLayer.h
    SllLayer.h
    TLVData.h
    TcpLayer.h
    TcpReassembly.h
    TextBasedProtocol.h
    UdpLayer.h
    VlanLayer.h
    VxlanLayer.h
    )

add_sources(packetpp 
    FILES_VAR PacketPPHeader 
    BASEDIR ${CMAKE_CURRENT_LIST_DIR} 
    PUBLIC ${PacketPPHeaderNames})
