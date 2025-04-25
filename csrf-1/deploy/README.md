### Basic CSRF challenge
---
This challenge uses Flask same as previous challenges. 
It has endpoint ```/admin/notice_flag``` which append flag to ```memo_text``` if ```userid=admin``` and ```IP=127.0.0.1```.
However, the server filters 3 keywords ```["frame", "script", "on"]```. Therefore, we can't use ``` <script> ``` to exploit. The solution is to use ``` <img> ``` with src attribute.
The payload will be ``` <img src="/admin/notice_flag?userid=admin"> ```. Then, obtain the flag at endpoint /memo.

![image](https://github.com/user-attachments/assets/b7aa7f1f-ca1b-4838-ac13-749519139050)
