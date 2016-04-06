# plesk_mailcert
Copys Plesk LetsEncrypt CERT to Mailservers and Webmin
Script Version: 1.05

The script MAILCERT is used if you secured your plesk server also with an LetsEncrypt certificate, Example: server.mydomain.tld

WARNING! This is experimental and only tested on Debian Systems at this time. Make sure you have backed up your PEM files before usage

Supported:

- Plesk 12.5
- Debian
- Postfix
- Dovecot
- Courier
- Webmin
- QMail

Usage:
- Install the LetsEncrypt Plesk Extension: https://github.com/plesk/letsencrypt-plesk
- Add a webspace with your plesk hostname and secure it with as LetsEncrypt certificate
- Edit MAILCERT script and set the hostname to server.mydomain.tld
- Run it manually or set up a monthly cron job

Remarks:
The MAILCERT Script try's to get the actual PEM File from the vhost. This file is changed after each renewal of the LetsEncrypt certificate. If the file exists, it will be copied to the known default pem file of the services.
At this time:
- Dovecot: /etc/dovecot/private/ssl-cert-and-key.pem
- Postfix: /etc/postfix/postfix_default.pem 
- Courier IMAP: /usr/share/imapd.pem
- Courier POP3: /usr/share/pop3d.pem
- Webmin: /etc/webmin/miniserv.pem
- QMail: /var/qmail/control/servercert.pem

If you have any questions or will get support please contact us at https://forum.powie.de