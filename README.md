# AWS-Full-Scale-Project
A small tier website having frontend, backend and database which takes values such as name and age and store it in database.
![image](https://github.com/user-attachments/assets/7fc1575e-73b5-4f8c-82f0-8fd21b912e26)
Now pulled that code into AWS instance to run the whole application on AWS.
First Created a VPC and inside that VPC created 6 private subnet and 2 public subnet
![image](https://github.com/user-attachments/assets/341364cb-57dc-4ffe-ac79-d8b8f0b71a44)
![image](https://github.com/user-attachments/assets/d589c8f2-c67a-4c32-8e95-306a0cc1dcb6)
To get communication via internet Internet Gateway is created and for prrivate subnet to communicate Nat gateway is created inside public subnet and through Route Table communication between these things is established.
![image](https://github.com/user-attachments/assets/e81169fe-7fd6-424f-9890-8913057d6397)
![image](https://github.com/user-attachments/assets/9026ed4f-17ef-47b5-aebc-22b66ccc0a71)
![image](https://github.com/user-attachments/assets/fe3f4476-cc8f-4634-bdfa-d2744fee8375)
From outside to communicate with frontend which is inside private subnet and for that frontend to communicate with backend which is also inside private subnet 2 Load Balancers are created.
![image](https://github.com/user-attachments/assets/5a7c11b0-3c19-4971-a700-a2c008fcd230)
![image](https://github.com/user-attachments/assets/67527d46-a9e6-4051-90ec-46db561213e0)
Mysql Database is created inside private subnet and also created one EC2 instance for installing and using MySQl.
Used Bastion Host to communicate with private EC2 instances.
![image](https://github.com/user-attachments/assets/8d355198-5208-4dcb-805c-eb9a7e3a56d6)
![image](https://github.com/user-attachments/assets/235693e7-364e-4eba-991d-120beb40e27f)
Inside web tier there is file named Addstudent.js there pasted the DNS name of second Load Balancer named AppTierLB and inside app tier there is file named app.js there in hostname pasted the endpoint of database and also username of database and in encoded way password.
![image](https://github.com/user-attachments/assets/d6289d14-9fb1-4f60-94ff-ff8af02985c9)
Now logged in into "WebTierEC21a" and "AppTierEC21a" which i named the instance and both are in private subnet so with the help of bastion host logged in and ran the command "npm start" and "node app.js" respectively.
![image](https://github.com/user-attachments/assets/3fd277d7-0c32-4700-9d11-63ce203eb6bb)
![image](https://github.com/user-attachments/assets/a8f243db-c8ef-438a-9e70-f8083ccd3088)
Website successfully responded to first Load Balancer DNS which is named as "WebTierLB".
Then inserted the values.
![image](https://github.com/user-attachments/assets/13269ca5-c763-424d-bd5f-9eaf9e86c01f)
![image](https://github.com/user-attachments/assets/54e47a30-6a7a-4b78-bf23-6afb00f4cd55)
![image](https://github.com/user-attachments/assets/a36d71a8-9711-4ab6-97d5-c9ef9622b333)
After that to check the flow I logged into MySQL EC2 instance.
![image](https://github.com/user-attachments/assets/ea1b4c3c-9531-4a85-ab3b-b47c46812786)
![image](https://github.com/user-attachments/assets/08f1856e-0703-4218-beb3-1dec43472a93)
For further updates we can write a Terraform Script for other availability zones and through Route53 can manage the traffic.

ThankYou :) 





