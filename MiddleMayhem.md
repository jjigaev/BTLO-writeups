<img width="590" height="352" alt="image" src="https://github.com/user-attachments/assets/71b30bc6-bba2-4709-b78b-e4812459213c" />
<img width="1228" height="223" alt="image" src="https://github.com/user-attachments/assets/88c09418-0855-4b3f-9053-7e90dcd080cd" />

## Access the Website in the browser, present it in the bookmark, and identify the JavaScript framework and version used. (2 points)
I was a little stuck on this simple question since i didnt know where to start. But then I got my bearings and accessed Firefox to website MiddleMayhem
Since it was our target, it was necessary to look through the website.
<img width="618" height="94" alt="image" src="https://github.com/user-attachments/assets/5aad5c10-2e85-4fe6-bce3-0957d369748e" />
Here is answer itself.
Answer: Next.js 15.0.0
## Using Splunk, Find the attacker’s IP address (3 points)
I initially needed quite some time to learn Splunk, since it was 1st i am interacting with it. Since i got familiar with its language, i got to work. 
Firstly, i checked through index all events. I failed
I gone through several searches checking networks, but then i got to searches for web app. <img width="1132" height="499" alt="image" src="https://github.com/user-attachments/assets/b82628c1-dfcf-484b-8edf-a5761404965d" />
 172.217.164.174 was in the first, it is not suspicious one.
 Then it should be 218.92.0.204, i checked this and found suspicious shell with nc
 <img width="1068" height="442" alt="image" src="https://github.com/user-attachments/assets/784540b8-890d-4cf9-a3d9-2392c6b1c57b" />
Answer: 218.92.0.204

## Analyze the SIEM logs to determine how many unique URIs were accessed by the attacker. (2 points)
Through several examining of different searches. I found the most successfull one.
<img width="1690" height="611" alt="image" src="https://github.com/user-attachments/assets/37a83662-1fe0-4dda-b082-e5240344a3a1" />
Turn off event sampling for full search.
<img width="492" height="118" alt="image" src="https://github.com/user-attachments/assets/4a047f3b-5df1-4cff-ad40-40d5399f5e18" />
Answer: 9930

## Explore the site and identify two specific locations that could reveal internal structures or potential access points not meant for public eyes. Provide the two relative URLs. (3 points)
"Explore the site". When exploring the website i found Robots.txt that showed 2 URLs
<img width="771" height="262" alt="image" src="https://github.com/user-attachments/assets/7acc9a2d-d5c8-4ae9-90bf-8434e41fe8b0" />
Answer: /admin, /admin/file-upload

## Based on the Framework and Version, what recent CVE could be used to bypass authorization? (4 points)
Google
<img width="1289" height="721" alt="image" src="https://github.com/user-attachments/assets/7f1d7032-de48-48b7-b5c3-f5accfe6ae5f" />
Answer: CVE-2025–29927
## Find the relevant HTTP header in the SIEM logs that indicates CVE exploitation. Provide the header name. (3 points)
<img width="1305" height="534" alt="image" src="https://github.com/user-attachments/assets/38ffcf0f-38d9-463d-a59f-a743b2ec3100" />
We identified request header. Lets search by this
<img width="1636" height="80" alt="image" src="https://github.com/user-attachments/assets/1a25590d-0ee2-4a64-8038-6324ec927ed0" />
Answer: X-Middleware-subrequest:middleware

## What interesting URI did the attacker access after exploiting the CVE? (3 points)
<img width="572" height="60" alt="image" src="https://github.com/user-attachments/assets/ddcfc68e-ab35-4359-824a-e1b0f311f040" /> 
the first event from previous search for middleware
Answer: /api/upload
## The attacker tried uploading a reverse shell. Find out the IP and port to which the target would connect once the connection is established. (2 points)
Later in the first questions i found then some interesting command in requests like "nc" that is used for remote shell.
<img width="598" height="78" alt="image" src="https://github.com/user-attachments/assets/59dd878f-cede-4b2a-bb4b-77c9e41f538b" />
<img width="1236" height="300" alt="image" src="https://github.com/user-attachments/assets/41eafa6e-19c0-45fc-8cbd-3cca7a0ee78d" />
Answer: 113.89.232.157 31337

## After compromising the WebApp server, the attacker attempted lateral movement. Identify the technique used, as recorded in the SIEM logs. (2 points)
"SIEM logs" - means we need to analyze logs. We analyze logs with searching for index
<img width="1588" height="510" alt="image" src="https://github.com/user-attachments/assets/3f05bd36-88ce-446a-9cbe-c1725ae5c2f7" />
Well looking to attempt numbers, it seems like SSH bruteforce.
<img width="1238" height="117" alt="image" src="https://github.com/user-attachments/assets/117ec9dd-4441-48e3-91ab-1274fa0bd690" />
Answer: SSH bruteforce
## Identify the user account that achieved successful lateral movement to another server. (1 points)
This was the most long one since i started with false trail. I initially searched for "username", "success:". But i should have searched for "Password"
because it was about Successfull password login.
<img width="1634" height="509" alt="image" src="https://github.com/user-attachments/assets/8a688ad5-5e8a-467d-beb4-d801f122002c" />
Answer:dbserv

That wass all for today. I gain the knowledge of working with SIEM logs via Splunk.
