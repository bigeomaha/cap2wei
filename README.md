cap2wei
=======

Simple scripts to convert HUAWEI TMF binary/text traces to PCAP / PLAIN LOGs

### Disclaimer
The scripts were hacked together quite fast and barely tested, use at your own risk!
Supports only text input format at this time, extracted using official vendor tools, etc.


## Requires:

- perl
- text2pcap (wireshark)
- bit-twist (http://bittwist.sourceforge.net )

## Usage for BINARY PTMF:
```
./ptmf2pcap.pl {filename.ptmf}
```

## Usage for TEXT PTMF:
```
./cap2wei.pl {filename.txt}
```


### Output Files:
```
PCAP: {filename}.pcap
LOG:  {filename}.log
```

### Header Formats:
```
 	[No.                   ] INT
 	[TimeStamp             ] %Y-%m-%d %H:%M:%S.
 	[Source Address        ] IPv4
 	[Source Port           ] INT
 	[Destination Address   ] IPv4
 	[Destination Port      ] INT
 	[Message Interface Type] STRING
 	[Message Type          ] STRING
 	[Hex Message           ] HEX
```
