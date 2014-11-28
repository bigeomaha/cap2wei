cap2wei ("kept-away")
=======

**PTMF** is a headache-inducing tracing format utilized by chinese manufactor *HUAWEI* in their SIP/IMS voice equipment, completely undocumented and not currently supported by any external application.

**ptmf2pcap** *(binary)* and **cap2wei** *(text)* are a pair a simple, ugly & brutal script which attempt decoding and converting of *HUAWEI TMF* binary/text traces to *PCAP / PLAIN TEXT* based on reverse engineering of the protocol alone, and leaves much to be desired. Extraction of SIP Payload and Injection of original IP:PORT and TimeStamp from TMF header to PCAP is mostly supported.

### Disclaimer
The scripts were hacked together quite too fast and barely tested, use at your own risk!

If you wish to contribute further PTMF samples to improve the script, contact the author.


### Scripts:
```
- ptmf2pcap.pl  : Convert binary PTMF to .PCAP and clear-text .LOG
- cap2wei.pl    : Convert text PTMF (?) to .PCAP and clear-text .LOG
```
### Requirements:

- perl
- text2pcap (wireshark)
- bit-twist (http://bittwist.sourceforge.net )

## Usage for BINARY PTMF files:
```
./ptmf2pcap.pl {filename.ptmf}
```

## Usage for TEXT PTMF exports:
```
./cap2wei.pl {filename.txt}
```


### Output Files:
```
PCAP: {filename}.pcap
LOG:  {filename}.log
```

### Text Format: Headers (work in progress)
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
