![alt text](https://raw.githubusercontent.com/51j0/Android-CertKiller/master/res/network.png "icon")

## Android-TrustCertificate
###### v0.1-alpha

### Install Custom CA as a system-level trusted CA

```bash
root@51j0 openssl x509 -inform DER -in cacert.der -out cacert.pem
root@51j0 openssl x509 -inform PEM -subject_hash_old -in cacert.pem |head -1
root@51j0 mv cacert.pem <hash>.0  

root@51j0 adb root   #Optional
root@51j0 adb remount #Optional
root@51j0 adb push <cert>.0 /sdcard/
root@51j0 mount -o rw, remount /system
root@51j0 mv /sdcard/<cert>.0 /system/etc/security/cacerts/
root@51j0 chmod 644 /system/etc/security/cacerts/<cert>.0  
root@51j0 mount -o rw, remount /system
```

![alt text](https://raw.githubusercontent.com/51j0/Android-Storage-Extractor/master/res/android.png "icon")
<div>Icons made by <a href="https://www.freepik.com/" title="Freepik">Freepik</a> from <a href="https://www.flaticon.com/" 			    title="Flaticon">www.flaticon.com</a> is licensed by <a href="http://creativecommons.org/licenses/by/3.0/" 			    title="Creative Commons BY 3.0" target="_blank">CC 3.0 BY</a></div>
