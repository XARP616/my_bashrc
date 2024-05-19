# Security

## Auditing

### Automatic Linux auditing (blue team)
```bash
sudo apt install -y lynis
sudo lynis audit system
```
* Automated security auditing
* Compliance testing (e.g. ISO27001, PCI-DSS, HIPAA)
* Vulnerability detection
* Configuration and asset management
* Software patch management
* System hardening
* Penetration testing (privilege escalation)
* Intrusion detection

Audiences
* System administrators
* Auditors
* Security professionals

[Repo](https://github.com/CISOfy/lynis)

### Vuls: Automatic vulnerability lookup


[Repo](https://github.com/future-architect/vuls)

[Scan](https://vuls.io/docs/en/usage-scan.html)

* [Host install](https://vuls.io/docs/en/install-with-vulsctl-host.html)
  Download scripts from linked repo!!
  
* [Vulsctl](https://vuls.io/docs/en/install-with-vulsctl.html)
* [Manual install](https://vuls.io/docs/en/install-manually.html)
* [Docker install](https://vuls.io/docs/en/install-with-docker.html)
* Also install with Anisble and other methods.

## Networking

### IP Spoofing w/ `iptables`
Quizá fuese posible posible recuperar las respuestas por medio de ARP spoofing en LAN. Además, sería necesario otra regla de iptables de forward para rebotar a localhost las tramas destinadas a la IP falsificada.

[Address Spoofing with iptables in Linux](https://sandilands.info/sgordon/address-spoofing-with-iptables-in-linux)

### Security testing w/ `JMeter`
Different testing techniques with Apache JMeter.
* Site Spidering
* Regular Expression Extractor
* XPath Extractor
* CSS/JQuery Extractor
* HTML Link Parser
* Fuzzing
* DDoS

[Blazemeter - How To Do Security Testing With JMeter](https://www.blazemeter.com/blog/security-testing-jmeter)

## Injection

### Bash protection against injection
Interestingly, it does not use a blocklist, instead, it cleverly greps out the path.

[Read here](https://stackoverflow.com/questions/56687976/what-are-the-possible-list-of-linux-bash-shell-injection-commands#answer-56688189)
[Sanitize user input](https://linuxconcept.com/write-bash-script-for-sanitizing-user-input-and-for-repeatable-results/#better_inputsh)
[User input validation](https://savvyadmin.com/bash-user-input-validation/)

### Shell script security
[Apple's Guide to shell script security](https://developer.apple.com/library/archive/documentation/OpenSource/Conceptual/ShellScripting/ShellScriptSecurity/ShellScriptSecurity.html#//apple_ref/doc/uid/TP40004268-CH8-SW1)

### Advanced shell scripting guide
[Read here](https://tldp.org/LDP/abs/html/)

## Logging

Automatic scan for logs:
```bash
sudo apt install logcheck
sudo -u logcheck logcheck -o -t
```

## System 

### Check dependencies and packages (good practice)
```bash
sudo apt-cache show [PACKAGE_NAME]
```

# Audit

## System audit

### Msfvenom
Msfvenom can be used to export Metasploits' payloads.

* In the following cheatsheet, we can find binaries and payload examples for meterpreter and other reverse shells.
  
  [MSFVenom Reverse shell payloads](https://infinitelogins.com/2020/01/25/msfvenom-reverse-shell-payload-cheatsheet/)

* In this other article, we can find some parameters to adjust the formats and platforms for the exported payloads
  
  [MSFVenom cheatsheet: Windows Exploitation](https://www.hackingarticles.in/msfvenom-cheatsheet-windows-exploitation)

* This other article analyzes metasploit shellcodes at low level

  [A look at Metasploit's Shellcodes](https://hidocohen.medium.com/a-look-at-metasploits-shellcodes-4c21de5e4580)

### Shellcode to assembly / binary to ASM
[How to convert shellcode to readable assembly code/instructions?](https://stackoverflow.com/questions/65471634/how-to-convert-shellcode-to-readable-assembly-code-instructions)

# Cryptography

### Cipher files with OpenSSL

```bash
openssl enc -cipher [-help] [-ciphers] [-in filename] [-out filename] [-pass arg] [-e] [-d] [-a] [-base64] [-A] [-k password] [-kfile filename] [-K key] [-iv IV] [-S salt] [-salt] [-nosalt] [-z] [-md digest] [-iter count] [-pbkdf2] [-p] [-P] [-bufsize number] [-nopad] [-debug] [-none] [-rand file...] [-writerand file] [-engine id]
```

Example
```bash
openssl enc -aes-256-cbc -md sha512 -pbkdf2 -iter 1000000 -salt -in InputFilePath -out OutputFilePath
```
**Decryption is issued simply by adding `-d` switch to the end of the original command-line.**

[Read here](https://askubuntu.com/questions/1093591/how-should-i-change-encryption-according-to-warning-deprecated-key-derivat#answer-1126882)
