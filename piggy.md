<img width="623" height="523" alt="image" src="https://github.com/user-attachments/assets/842be4a6-52fa-4d52-bc84-5d32a93f584a" />
<img width="1209" height="176" alt="image" src="https://github.com/user-attachments/assets/a279e919-1f85-49d3-91e2-f1c447e428b7" />

# PCAP One) What remote IP address was used to transfer data over SSH? (Format: X.X.X.X) (3 points)
<img width="1915" height="555" alt="image" src="https://github.com/user-attachments/assets/46158e51-897e-4640-a117-37bb8d56fe21" />
<img width="1864" height="258" alt="image" src="https://github.com/user-attachments/assets/471dbbd8-8cbe-4ce6-8b0a-3eef5d253cde" />
Answer: 35.311.33.16
# PCAP One) How much data was transferred in total? (Format: XXXX M) (3 points)
Look at the >Statistics tab again.
<img width="1376" height="95" alt="image" src="https://github.com/user-attachments/assets/1e33554c-4b46-4ba5-8af5-5ba8e237a7e8" />
Answer: 1131 M
# PCAP Two) Review the IPs the infected system has communicated with. Perform OSINT searches to identify the malware family tied to this infrastructure (Format: MalwareName) (3 points)
After a long investigation of different methods of finding malware path by TLS and DNS packets, first, i tried to find strange domain names in DNS. Then, i tried to find JA3 in TLS protocol.
Finding nothing, i decided to bruteforce all IP addresses in VirusTotal.
<img width="1919" height="879" alt="image" src="https://github.com/user-attachments/assets/45527208-be9e-4f3a-9cb2-ceccad5b655e" />
This it it. Sometimes, questions need easy answers.
Answer: Trickbot 
# PCAP Three) Review the two IPs that are communicating on an unusual port. What are the two ASN numbers these IPs belong to? (Format: ASN, ASN) (3 points)
<img width="389" height="133" alt="image" src="https://github.com/user-attachments/assets/2333b03b-76a6-45e4-a969-7e230aafb4b4" />
<img width="1899" height="363" alt="image" src="https://github.com/user-attachments/assets/b9c84023-d613-4437-806f-7e2a18eed8cc" />
<img width="1917" height="542" alt="image" src="https://github.com/user-attachments/assets/da6997a8-2a98-4ec8-9f7b-f80da2a64662" />
<img width="509" height="79" alt="image" src="https://github.com/user-attachments/assets/22e5012a-7a24-4384-8e74-5bb439f2cf5b" />
Answer: AS63949, AS14061
# PCAP Three) Perform OSINT checks. What malware category have these IPs been attributed to historically? (Format: MalwareType) (3 points)
<img width="1410" height="563" alt="image" src="https://github.com/user-attachments/assets/07a8c80a-9889-4e3b-8baa-48dd9eb7b513" />
Answer: Miner
# PCAP Three) What ATT&CK technique is most closely related to this activity? (Format: TXXXX) (3 points)
<img width="1372" height="258" alt="image" src="https://github.com/user-attachments/assets/fdd8f5f6-0412-4df6-8f66-1962161da95c" />
Answer: T1496
# PCAP Four) Go to View > Time Display Format > Seconds Since Beginning of Capture. How long into the capture was the first TXT record query made? (Use the default time, which is seconds since the packet capture started) (Format: X.xxxxxx) (3 points)
TXT query - is DNS query that contains txt information about domain. In wireshark, to search for this type of queries, we filter for type == 16.
<img width="1919" height="241" alt="image" src="https://github.com/user-attachments/assets/2c4e3ad9-3935-48b0-adc1-08bd1a2fdd5c" />
Answer: 8.527712
# PCAP Four) Go to View > Time Display Format > UTC Date and Time of Day. What is the date and timestamp? (Format: YYYY-MM-DD HH:MM:SS) (3 points)
<img width="1915" height="138" alt="image" src="https://github.com/user-attachments/assets/fb66d32c-72ac-4b24-8a0f-cf1823408d72" />
Answer: 2024-05-24 10:08:50
# PCAP Four) What is the ATT&CK subtechnique relating to this activity? (Format: TXXXX.xxx) (1 points)
Answer: T1071.004
<img width="1459" height="333" alt="image" src="https://github.com/user-attachments/assets/2277ad6e-4b3c-40d3-a49d-3959acb959f5" />

In this assignment, i learned more about OSINT tools and a little about filtering of Wireshark tool. Overall, the most difficult questions was 2nd, because i overcomplicated it. The most important information i gained was about the work TLS protocol.
