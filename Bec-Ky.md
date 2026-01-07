<img width="1280" height="496" alt="Снимок экрана 2026-01-07 145600" src="https://github.com/user-attachments/assets/d5913b0c-aa5d-45e8-9bcd-45c5c68ba7ef" />
Today we are working with phishing case. We will investigate the incident, we have emails and Azure audit logs.
## What is the source address of the initial phishing email? (5 points)
<img width="1548" height="825" alt="Снимок экрана 2026-01-07 150536" src="https://github.com/user-attachments/assets/dc6c38e5-4f75-42d5-b4d7-7966f312c803" />
Through careful examining of every email, we conclude that <img width="1485" height="985" alt="Снимок экрана 2026-01-07 151249" src="https://github.com/user-attachments/assets/8899b2e8-9e3d-4cad-96db-ed874c1feb0b" />
There was come initial red flags with the way email was written anyway.
Answer: sabastian@flanaganspensions.co.uk

## What type of compromise is this? (5 points)
Answer: <img width="1049" height="768" alt="Снимок экрана 2026-01-07 151528" src="https://github.com/user-attachments/assets/a63d807e-e199-4ec0-b0d5-012b34ba40fd" />
Initially i didnt understand the question, but then i searched for the types of email phishing attacks and found the right one.

## What are the two IPs utilised by the TA? (5 points)
This was the most difficult one, because i had some performance problems with VM of BTLO, so when seacrhing for answers in large augit logs like this
it was quite hard to narrow down the search.<img width="1461" height="60" alt="Снимок экрана 2026-01-07 153810" src="https://github.com/user-attachments/assets/2ab70d82-4d1c-427f-a8e4-73eeac6ce444" />
But i eventually found the answers focusing on Becky’s account — the victim mailbox. After correlating timestamps and account activity, i identified
2 suspicious sign-ups close to time of the events. <img width="1395" height="131" alt="Снимок экрана 2026-01-07 153832" src="https://github.com/user-attachments/assets/00ad5df2-fa54-4b47-b70e-f8882568d124" />

Answer: 159.203.17.81, 95.181.232.30

## Which bank is the transaction sent to? (2 points)
Answer: <img width="1283" height="752" alt="Снимок экрана 2026-01-07 153624" src="https://github.com/user-attachments/assets/0423c5f1-93f6-4fa4-942b-21c5709ecd3a" />
There was info in one email about transaction.

## What is the name of the Inbox folder created during the compromise? (4 points)
I searched for InboxRule, there was one rule created during the attack.
Answer: <img width="1297" height="60" alt="Снимок экрана 2026-01-07 155006" src="https://github.com/user-attachments/assets/ef044e8a-83c6-44f1-86cb-cf583ccf9e0e" />


## What word is the first inbox rule created looking for, within the subject or body, prior to deleting the email (4 points)
I searched for "DeleteMessage" rule to quickly find the rule crea<img width="1187" height="97" alt="Снимок экрана 2026-01-07 155245" src="https://github.com/user-attachments/assets/90566227-32a2-4465-8b37-d21afa86f05d" />
ted because TA usually uses this rule to cover up.
Answer: Withdrawal

<img width="1319" height="840" alt="Снимок экрана 2026-01-07 155300" src="https://github.com/user-attachments/assets/c2771157-ec3e-4d3a-a519-3b94ed925b4e" />

