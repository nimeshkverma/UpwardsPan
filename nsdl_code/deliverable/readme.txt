1) Following jars(bcmail-jdk16-144.jar,bcprov-jdk16-144.jar) are needed. JAR's are jdk version specific and can be downloaded from http://www.bouncycastle.org/latest_releases.html (Refer MIT X11 License available at http://opensource.org/licenses/mit-license.php for the license related information)


2) Set classpath in the following manner 

(on unix)
Open Terminal and type the following (Replace /path/to/ with the path to the respective files)

CLASSPATH=.:/Users/nimesh/Downloads/pan_api/bcmail-jdk16-144.jar:/Users/nimesh/Downloads/pan_api/bcprov-jdk16-144.jar:$CLASSPATH
export CLASSPATH


3) To convert pfx into a jks (java key store) run the keystore converter

java p2j certi.pfx pfxpswd oupt.jks

where certi.pfx is the name of the .pfx file containing the certificate and the private key, pfxpswd is the password of the pfx, oupt.jks is the name of the java key store which will be generated by executing p2j


4)To generate a pkcs7 signature run pkcs7gen 

java pkcs7gen oupt.jks pfxpswd dataToBeSigned oupt.sig

where oupt.jks is the name of the java key store created in step 3, pfxpwd is the password of the pfx, dataToBeSigned is the carrot delimited data consisting of user id and upto 5 pans and oupt.sig is the file where the detached pkcs7 signature will be stored

