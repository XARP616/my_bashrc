# Security

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
