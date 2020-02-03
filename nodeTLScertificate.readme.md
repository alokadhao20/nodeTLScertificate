1. There are two kinds of certificates: those signed by a 'Certificate Authority', or CA, and 'self-signed certificates'. 
2. A Certificate Authority is a trusted source for an SSL certificate, and using a certificate from a CA 

3. Create ssl certificates 

    COMMAND:- openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365 -nodes -subj '/CN=localhost'
        openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365 -subj '/CN=localhost' // if password has to give 

4. You can also add -nodes (short for no DES) if you don't want to protect your private key with a passphrase. Otherwise it will prompt you for "at least a 4 character" password.

5. The days parameter (365) you can replace with any number to affect the expiration date. It will then prompt you for things like "Country Name", but you can just hit E       Enter and accept the defaults.

6. Add -subj '/CN=localhost' to suppress questions about the contents of the certificate (replace localhost with your desired domain).

7. Self-signed certificates are not validated with any third party unless you import them to the browsers previously. 
    If you need more security, you should use a certificate signed by a certificate authority (CA).

