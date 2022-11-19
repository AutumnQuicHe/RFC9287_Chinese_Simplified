---
title: "1. 引言"
anchor: "1_Introduction"
weight: 100
rank: "h1"
---

The version-independent definition of QUIC [QUIC-INVARIANTS] intentionally describes a very narrow set of fields that are visible to entities other than endpoints. Beyond those characteristics that are invariant, very little about the "wire image" [RFC8546] of QUIC is visible.

在与版本无关的QUIC定义《[QUIC不变量]()》中描述了少量对于并非终端的实体可见的字段。
除了那些不可变的特征外，QUIC的“线路图像”（`wire image`， 详见《[RFC8546]()》）几乎是不可见的。

The second-most significant bit of the first byte in every QUIC packet is defined as having a fixed value in QUIC version 1 [QUIC]. The purpose of having a fixed value is to allow endpoints to efficiently distinguish QUIC from other protocols; see [DEMUX] for a description of a system that might use this property. As this bit can identify a packet as QUIC, it is sometimes referred to as the "QUIC Bit".

在QUIC版本1中（详见《[QUIC]()》），所有QUIC数据包的首个字节的第二最高有效位被指定为固定值。
设定该固定值的目的是为了与允许终端高效地将QUIC从其他协议中区分出来；有关可以利用该属性的系统的描述，详见《[DEMUX]()》。
由于能够使用该比特位来辨识数据包是否为QUIC，因此它有时被称为“QUIC位”。

Where endpoints and the intermediaries that support them do not depend on the QUIC Bit having a fixed value, sending the same value in every packet is more of a liability than an asset. If systems come to depend on a fixed value, then it might become infeasible to define a version of QUIC that attributes semantics to this bit.

在支持QUIC的终端和中间设备并不要求QUIC位必须是固定值的情况下，在所有数据包中都使用相同的值的做法相比其好处，更多的是一种负担。
相反，如果这些系统都依赖着固定值，那么就不可能再定义一个为该比特位添加语义的QUIC版本。

In order to safeguard future use of this bit, this document defines a QUIC transport parameter that indicates that an endpoint is willing to receive QUIC packets containing any value for this bit. By sending different values for this bit, the hope is that the value will remain available for future use [USE-IT].

为了保护该比特位将来的用途，本文档定义了一个QUIC传输参数，它能表明终端愿意接收该比特位被设置为其他值的QUIC数据包。
通过释放对该比特位的限制，希望能够在将来随时利用该位的值（详见《[USE-IT]()》）。
