# To setup HTTPS secured certificate with java
------------------

## For *localhost*
- Create selfsigned certificate using `keytool -genkey` command.
  e.g. keytool -genkey -alias selfsigned -keyalg RSA -keystore thekeystore.jks -keysize 2048
- Setup your server (tomcat / dropwizard) with that certificate
- Download / Save certificate file from browser
- Import the certificate file using `keytool -import` command.
  e.g. sudo keytool -import -trustcacerts -alias localhost -keystore "/Library/Java/JavaVirtualMachines/jdk1.8.0_121.jdk/Contents/Home/jre/lib/security/cacerts" -file localhost.cer
- Restart the server

## Other useful links:
- What is a CSR (Certificate Signing Request)? - https://www.sslshopper.com/what-is-a-csr-certificate-signing-request.html
- Getting Chrome to accept self-signed localhost certificate - https://stackoverflow.com/questions/7580508/getting-chrome-to-accept-self-signed-localhost-certificate