## In Cockpit CMS v2.6.3, I found Stored-XSS in upload assets feature
Cockpit CMS v2.6.3
Installation: https://github.com/Cockpit-HQ/Cockpit
## Reproduce bug:
Step 1: Access to http://localhost/Cockpit/auth/login?to=%2F and log in to an account that has permission to upload assets. Go to Assets and click "Upload Asset" button to upload file.

![Alt text](image1.png)

Step 2: In upload feature, inject payload XSS: <img src=x onerror=alert('XSS_by_NCS');> into content file, and filename has the extension .shtml

![Alt text](image2.png)

Step 3: Access to images by using link in "Copy asset link"

![Alt text](image3.png)

And XSS payload will execute
 
![Alt text](image4.png)
