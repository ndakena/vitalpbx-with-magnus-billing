# vitalpbx-with-magnus-billing
How to use Magnus Billing for VitalPBX real time billing.

---
I am going straightforward to the process, but before then, I will share a simple architecture of what I am setting up. Additionally, I will mention the results I want to obtain. Ready? Lets get started.
![image](https://user-images.githubusercontent.com/30364345/194750346-ebadc986-1fac-446b-acd9-08c001cf1520.png)

As can ben seen above, extensions in VitalPBX can call via telnyx SIP Trunk and get charged by Magnus Billing. I will list the necessary parts below
### Step 1: Create "client" users in Magnus Billing
Since you want extensions to be charged by Magnus billing, you need to create client users in MB whose billing account would be used by it's SIP users. To this user, you need to assign a plan, which is linked to a particular trunk group. In my case, I only have one trunk in my Trunk group and the trunk is a Telnyx SIP trunk.
![image](https://user-images.githubusercontent.com/30364345/194760580-1a93cf2f-1d8a-427c-8549-b238d4ede263.png)

Though I have only one SIP trunk for now, I am using LCR routing because when I will add SIP trunks, calls will choose a trunk based LCR strategy.
![image](https://user-images.githubusercontent.com/30364345/194760724-2e92f045-290f-4386-9da3-bf5d0e25b671.png)

