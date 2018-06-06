### Introduction
When one consumes a secured url or https url it gives an SSLHandshake exception. The below steps will help to remove this error
and successfully consume a https or secured url.

#### Steps To Consume A Https URL Or Endpoint in Java

1. Open the URL in browser
2. Click on the Green pad(For all Valid Certificates) icon in the browser
3. Open the certificate, go to details and choose copy to file
4. Go through the Export Certificate Wizard, choose DER encoded binary X.509 (.CER) option and complete it
5. Using the _keytool_ utility check for the number of existing certificates
  
    _keytool -list -keystore "%JAVA_HOME%/jre/lib/security/cacerts"_

   Note: The default password is "changeit"
6. keytool -import -alias <any name> -keystore "%JAVA_HOME%/jre/lib/security/cacerts" -file <location to .cer file>
7. After this the count to the number of certificates should increase by 1 which indicates that the certificate import was successful


