<img width="1876" height="533" alt="image" src="https://github.com/user-attachments/assets/970bdb22-aa58-410c-a8a3-cc7a6673673c" />
Downloading the file will open us zip file with several. I saw .doc file "sample.doc". It seems to have some Remote Code Execution through Office file scripts.
Opening the file could allow attackers to execute malicious code and compromise the system. Analyzing the file enables identification of malicious payloads, 
confirmation of whether the vulnerability is being exploited, and discovery of indicators of compromise (IoCs), all of which are essential for understanding the attack and strengthening defenses.
Sha1 is 06727ffda60359236a8029e0b3e8a0fd11c23313.
We will use VirusTotal. 

# Question 1) What is the SHA1 hash value of the sample? (Format: SHA1Hash) (1 points)
Answer: 06727ffda60359236a8029e0b3e8a0fd11c23313

# Question 2) According to VirusTotal, what is the full filetype of the provided sample? (Format: X X X X) (1 points)
<img width="1838" height="729" alt="image" src="https://github.com/user-attachments/assets/e1bb125d-7251-4664-92b7-ff14543d6979" />
Answer: Office Open XML Document

# Question 3) Extract the URL that is used within the sample and submit it (Format: https://x.domain.tld/path/to/something) (1 points)
DOCX files are essentially ZIP archives containing XML files. You can unzip the file to inspect its contents. 
So, to extract a URL from a sample document we need to unzip sample.docx to reveal files.
By examining the document.xml.rels file located at word/_rels/document.xml.rels, you can see an XML relationships file that lists links to various resources. 
Within this file, a relationship with the ID rId996 was found, pointing to the target URL: https://www.xmlformats.com/office/word/2022/wordprocessingDrawing/RDF842l.html.
Answer: https://www.xmlformats.com/office/word/2022/wordprocessingDrawing/RDF842l.html
# Question 4) What is the name of the XML file that is storing the extracted URL? (Format: file.name.ext) (1 points)
<img width="1612" height="95" alt="image" src="https://github.com/user-attachments/assets/c029a03e-7f6c-48ce-9a30-f23a86742e4f" />
The XML file that stores the extracted URL is document.xml.rels.
Answer: document.xml.rels
# Question 5) The extracted URL accesses a HTML file that triggers the vulnerability to execute a malicious payload. According to the HTML processing functions, any files with fewer than <Number> bytes would not invoke the payload. Submit the <Number> (Format: Number of Bytes) (1 points)
Well lets do OSINT. We know the CVE.
<img width="969" height="846" alt="image" src="https://github.com/user-attachments/assets/99d20162-2ad7-4239-b59d-195e8c70c27e" />
Answer: 4096
# Question 6) After execution, the sample will try to kill a process if it is already running. What is the name of this process? (Format: filename.ext) (1 points)
Thanks to ahnlab report for this CVE
<img width="1469" height="700" alt="image" src="https://github.com/user-attachments/assets/afb53976-59e1-4270-be08-1a456f72318b" />
Answer: msdt.exe
# Question 7) You were asked to write a process-based detection rule using Windows Event ID 4688. What would be the ProcessName and ParentProcessname used in this detection rule? [Hint: OSINT time!] (Format: ProcessName, ParentProcessName) (1 points)
I used chatgpt
<img width="1053" height="248" alt="image" src="https://github.com/user-attachments/assets/cf5f1bd0-8fa7-4ae5-884f-112cd97970bc" />
Answer: mshta.exe, winword.exe
# Question 8) Submit the MITRE technique ID used by the sample for Execution [Hint: Online sandbox platforms can help!] (Format: TXXXX) (1 points)
Look in VirusTotal
<img width="409" height="178" alt="image" src="https://github.com/user-attachments/assets/c3600800-2008-4e1f-9e7e-7e5215f85b28" />
Answer: T1559
# Question 9) Submit the CVE associated with the vulnerability that is being exploited (Format: CVE-XXXX-XXXXX) (2 points)
<img width="150" height="65" alt="image" src="https://github.com/user-attachments/assets/7b37cdbc-0c8b-43d8-9473-d5c16febad5a" />
Answer: cve-2022-30190
<img width="1387" height="751" alt="image" src="https://github.com/user-attachments/assets/3b17dc91-314e-46eb-96ec-f26a1c09f369" />

In this writeup, I learned the .doc files can be unzipped and contains .xml files. We extracted information from this files.
