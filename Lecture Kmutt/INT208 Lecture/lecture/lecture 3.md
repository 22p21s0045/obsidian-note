3/12/2024
[[Network security.pdf]]
#security #lecture-3
## Security component
- end to end
“End-to-end security” refers to a comprehensive approach to protecting data, communications, and operations across an entire system or network. It involves implementing security measures at <mark class="hltr-yellow">every stage</mark>, from the initial data creation or collection point to its final destination. [This ensures that sensitive information remains confidential, maintains its integrity, and is available to authorized users when needed](https://www.kiteworks.com/secure-email/secure-email-end-to-end-security/)[1](https://www.kiteworks.com/secure-email/secure-email-end-to-end-security/)[2](https://learn.microsoft.com/en-us/azure/security/fundamentals/end-to-end).

## INFORMATION (VISUALIZATION) ERA
- Information needs to be hidden from unauthorized access
- Protect from unauthorized
- authorized entity when it is needed

## Priority of trust device

![](https://i.imgur.com/YRTaTJZ.png)


![](https://i.imgur.com/QcJTT6N.png)
- **Snooping** เเอบดูข้อมูล
- **Masquerading** ดักระหว่างทางเเล้วปลอมเเปลงเเทน
- **Replaying** ทําซํ้าควรจะไม่ได้
- **Repudiation** การปฎิเสธ
#attack 
## Denial of service (Dos)
- ถูกโจมตีจนต้องหยุดให้บริการ

## Intranet risk (ความเสี่ยงภายใน)
- **Intercepting Network Messages (ดักจับ)**: This is commonly known as **sniffing**. It involves capturing network traffic, which can include sensitive information like user IDs, passwords, and financial data. Encryption and secure communication protocols are essential to protect against this.

- **Accessing Corporate Databases**: When employees have connections to central databases, there’s a risk that sensitive data could be accessed improperly. Implementing strict access controls and monitoring can help mitigate this risk.

- **Privileged Employees (สิทธิพิเศษ)**: Employees with override privileges can potentially access mission-critical data without authorization. The principle of least privilege, where users have only the access necessary for their job, can help prevent abuse.

- **Reluctance to Prosecute (ความลังเลใจ ในการเอาผิด/ดําเนินคดี)**: Sometimes organizations may hesitate to take legal action against cybercrimes due to fear of negative publicity. However, this can embolden criminals. It’s important for organizations to have clear policies and take decisive action against security breaches to deter criminal behavior

![](https://i.imgur.com/8rz4Naa.png)

## Dictionary attack
A dictionary attack is a type of cyber attack that involves systematically entering words from a list, such as those found in a dictionary, as passwords to gain unauthorized access to a system, account, or encrypted file. Attackers use extensive lists of the most commonly used passwords, popular pet names, fictional characters, or literally just words from a dictionary.
![](https://i.imgur.com/XwhfE4g.png)
![](https://i.imgur.com/1vqOFMD.png)
#attack 
## How does a memcached attack work?

A Memcached attacks operates similarly to all DDoS amplification attacks such as [NTP amplification](https://www.cloudflare.com/learning/ddos/ntp-amplification-ddos-attack/) and [DNS amplification](https://www.cloudflare.com/learning/ddos/dns-amplification-ddos-attack/). The attack works by sending spoofed requests to a vulnerable server, which then responds with a larger amount of data than the initial request, magnifying the volume of traffic.

Memcached amplification can be thought of in the context of a malicious teenager calling a restaurant and saying "I'll have one of everything, please call me back and tell me my whole order." When the restaurant asks for a callback number, the number given is the targeted victim’s phone number. The target then receives a call from the restaurant with a lot of information that they didn’t request.
![](https://i.imgur.com/XNa8sUw.png)

- Defense by block

>[!tip]
> Mac address authentiaction have database of MAC address for security

#encyption #key
## Symetric key
![](https://i.imgur.com/ZAZ5LSG.png)
A symmetric key in cryptography is a key that is used for both encryption and decryption of data. This means that the same key must be used to decrypt information that was encrypted with it. The key represents <mark class="hltr-yellow">a shared secret between two or more parties</mark> that can be used to maintain a private information link.
#encyption #digital-signature

## Asymetric key
Asymmetric encryption, also known as public-key cryptography, is a method of encryption that uses two different keys to encrypt and decrypt data. These are the **public key** and the **private key**. The public key can be shared with anyone, while the private key is kept secret by the owner. Here’s how it works:

- **Encryption**: The sender uses the recipient’s public key to encrypt the data.
- **Decryption**: The recipient uses their private key to decrypt the data.
#tips 
>[!tip]
>A **digital signature** is a cryptographic mechanism used to verify the authenticity and integrity of a digital message or document. It’s like an electronic fingerprint that is unique to both the document and the signer, ensuring that the document hasn’t been altered after signing and confirming the signer’s identity.

![](https://i.imgur.com/Nop8Zcv.png)

- VPN เข้ารหัสลับช่วงนึง

>[!tips]
>Now we use **AES encryption**

- Intrusion Detection system
- Intrusion prevention system

