1. Create SSL certificate with ```sh
openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365 -nodes -subj "/C=XX/ST=XXX/L=XXXXX/O=XXXX"```

2. set apache to deny any path exepect /PATH/TO/served

3. install conntrack, and set iptable so ```sh
iptables -A INPUT -m conntrack --ctstate NEW,RELATED,ESTABLISHED -j ACCEPT```
