# vitalpbx-with-magnus-billing
How to use Magnus Billing for VitalPBX real time billing.

---
I am going straightforward to the process, but before then, I will share a simple architecture of what I am setting up. Additionally, I will mention the results I want to obtain. Ready? Lets get started.
![image](https://user-images.githubusercontent.com/30364345/194750346-ebadc986-1fac-446b-acd9-08c001cf1520.png)

As can ben seen above, extensions in VitalPBX can call via telnyx SIP Trunk and get charged by Magnus Billing. I will list the necessary parts below
----
### Step 1: Create "client" users in Magnus Billing
Since you want extensions to be charged by Magnus billing, you need to create client users in MB whose billing account would be used by it's SIP users. To this user, you need to assign a plan, which is linked to a particular trunk group. In my case, I only have one trunk in my Trunk group and the trunk is a Telnyx SIP trunk.
![image](https://user-images.githubusercontent.com/30364345/194760580-1a93cf2f-1d8a-427c-8549-b238d4ede263.png)

Though I have only one SIP trunk for now, I am using LCR routing because when I will add SIP trunks, calls will choose a trunk based LCR strategy.
![image](https://user-images.githubusercontent.com/30364345/194760724-2e92f045-290f-4386-9da3-bf5d0e25b671.png)
---
### Step 2: Create a SIP user in Magnus Billing
We'll now go ahead to create a SIP user in MB and associate it with the user created previously. This SIP user would later be used as SIP trunk in VitalPBX
![image](https://user-images.githubusercontent.com/30364345/194761594-14edd1fd-08cf-4f1f-9bab-5746d03b1507.png)
---
### Step 3: Register the SIP user in VitalPBX as SIP Trunk
In vitalPBX, you will need to register the SIP user created in Magnus billing as SIP trunk in VitalPBX, making sure you are creating SIP Trunk ann NOT PJSIP.
![image](https://user-images.githubusercontent.com/30364345/194763919-37d2f382-6360-4bb3-9347-d65b4b586567.png)

### Step 4: Create extensions and outbound route
This step might seem simple, but it's tricky! You need to create extensions, then create outbound routes and associate them to specific routes. 
##### Note that in the feature, you might want to add new billing user accounts in Magnus billing and set up the exteions in VitalPBX. This mean, when you have more that two Magnus billing users, you will want to be sure that when an associated extension in VitalPBX makes call, the correct account is charged.
This means implies that we need to define default route/trunk for extension in VitalPBX


I am still rounding up with this article to include more details, however, if you need my support, send a mail to ndakena@gmail.com
