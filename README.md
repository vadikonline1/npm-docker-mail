# Nginx Proxy Manager + Docker Mailserver + SSL Certificates

Nginx Proxy Manager + SSL: https://nginxproxymanager.com/guide/#quick-setup

Docker Mailserver: https://github.com/docker-mailserver/docker-mailserver

You can use: docker-compose.yml or docker-portainer
SSL Certificates it must be for "mail.example.com"



<b>IF can use docker-compose.yml don't forget:

Volume:
  contrainer: /etc/letsencrypt   -> volume: (indicate the volume from npm where the certificates are included)   
</b>




After starting the container, apply the following commands in the console:
  1. setup config dkim 
  2. setup email add admin@example.com password (run every time to add account)
  3. postconf -e "inet_protocols = ipv4"
  4. setup config dkim
  5. postfix reload

  

Create Recorder from DNS:
  1. mail ->  A -> IN -> IP_Server
  2. @ or blank -> MX -> mail.example.com -> Priority: 10
  3. @ or blank -> TXT -> v=spf1 mx ~all or v=spf1 mx -all (v=spf1 a mx include:_spf.google.com ~all)



Check MX from your server:

https://toolbox.googleapps.com/apps/checkmx/

https://intodns.com/
