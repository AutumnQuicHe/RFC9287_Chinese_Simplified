---
title: "3. 传输参数：grease_quic_bit"
anchor: "3_The_Grease_QUIC_Bit_Transport_Parameter"
weight: 300
rank: "h1"
---

The grease_quic_bit transport parameter (0x2ab2) is defined for QUIC version 1 [QUIC]. This transport parameter can be sent by both client and server. The transport parameter is sent with an empty value; an endpoint that understands this transport parameter MUST treat receipt of a non-empty value of the transport parameter as a connection error of type TRANSPORT_PARAMETER_ERROR.

传输参数`grease_quic_bit`（值为`0x2ab2`）是为QUIC版本1（详见《[QUIC]()》）定义的。
客户端和服务器都可以发送该传输参数。
发送该传输参数时将值设置为空；理解该传输参数的终端{{< req_level MUST >}}将接收到此传输参数且其值为非空的情况视作类型为`TRANSPORT_PARAMETER_ERROR`（传输参数错误）的连接错误。

An endpoint that advertises the grease_quic_bit transport parameter MUST accept packets with the QUIC Bit set to a value of 0. The QUIC Bit is defined as the second-most significant bit of the first byte of QUIC packets (that is, the value 0x40).

宣告传输参数`grease_quic_bit`的终端{{< req_level MUST >}}接受QUIC位被设置为`0`的数据包。
QUIC位的定义是QUIC数据包的首个字节的第二最高有效位（也就是掩码`0x40`所指示的位）。
