FROM wordpress:latest

# Adding SMTP Email Support
RUN apt-get update && \
    apt-get install -y wget && \
   wget https://github.com/mailhog/mhsendmail/releases/download/v0.2.0/mhsendmail_linux_amd64 && \
   chmod +x mhsendmail_linux_amd64 && \
   mv mhsendmail_linux_amd64 /usr/sbin/mhsendmail && \
   apt-get clean

# PHP mail settings
RUN echo "sendmail_path = '/usr/sbin/mhsendmail --smtp-addr="mailhog:1025"'" > /usr/local/etc/php/conf.d/mail.ini
