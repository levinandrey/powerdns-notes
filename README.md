# powerdns-notes



### PowerDNS pdnsutil 

CREATE ZONE

    pdnsutil create-zone example.com

ADD DATA TO ZONE // Let's start by adding the root A-record and AAAA for IPv6 (makarainen.net)

    pdnsutil add-record example.com @ A 192.168.1.2
    pdnsutil add-record example.com @ AAAA 2a01:4f9:c010:30f4::1

ADD DATA TO ZONE // adding a subdomain (www)

    pdnsutil add-record example.com www A 192.168.1.2

ADD DATA TO ZONE // every domain needs name servers

    pdnsutil add-record example.com @ NS ns1.example.com

ADD DATA TO ZONE

    pdnsutil add-record example.com @ MX "10 example.com"

    pdnsutil add-record example.com 3600 TXT "google-site-verification=example-id"

MANAGE ZONES // check the information provided

    pdnsutil list-zone example.com

MANAGE ZONES // modify the zone (if changes do not miss update serial -> UPDATE SERIAL)

    pdnsutil edit-zone example.com



### Enable Syslog for PowerDNS 

Enable Logging in PowerDNS Recursor Config
Edit Systemd Unit File for PowerDNS to Allow Syslog
Enable Logging in rsyslog Config File

https://www.incredigeek.com/home/enable-syslog-for-powerdns-recursor/


