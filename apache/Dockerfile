FROM rafaelcgstz/magento2

RUN apt-get update
RUN apt-get install -y --no-install-recommends openssl ssl-cert

RUN openssl req $@ -new -x509 -days 365 -nodes -out /etc/apache2/apache.pem -keyout /etc/apache2/apache.pem -subj "/C=BR/ST=SaoPaulo/L=SaoPaulo/O=Mercado Pago/OU=MP/CN=local.mercadopago.com.br"
RUN chmod 600 /etc/apache2/apache.pem
RUN echo  "Listen 443" >> /etc/apache2/ports.conf

RUN a2enmod rewrite
RUN a2ensite default-ssl
RUN a2enmod ssl

EXPOSE 443
EXPOSE 80
EXPOSE 9007


