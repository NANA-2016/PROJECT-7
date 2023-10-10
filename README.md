# PROJECT-7

# IMPLEMENTATION  LOADBALANCERS WITH NGINX.

 Load balancers  help to ;

-  distribute  traffic efficienttly  across multiple servers 

- Optimize performance 

-  ensure availabilty of your web applications .

##  Setting Up Basic Load Balancer .

 Here we will set up NGINX as a loadbalancer as it its a software that can act as a 

- webserver 

-  reverse proxy

-  Load balancer 

## STEP 1 

 It involves setting up instances on AWS .

 Below screen shots shows the two instances set up.

![setting up instances](https://github.com/NANA-2016/PROJECT-7/assets/141503408/bc585e5f-e2f5-4cc8-a6b3-fd847e541a39)

 The screen shots below show details of the 2 instances that have been set up.

 ![Apache server 1 details](https://github.com/NANA-2016/PROJECT-7/assets/141503408/e4174392-c436-47af-a912-67c5ce4958d5)

![apache server2 details](https://github.com/NANA-2016/PROJECT-7/assets/141503408/c068e904-8bc9-4641-bfd5-2ef588233ad2)

## STEP 2

 The webservers wwill be running on port 8000 and we need to allow traffic from anywhere .

These is done by changing the inbound rules as shows below for both servers .

Apache server 1

![port 8000  server 1](https://github.com/NANA-2016/PROJECT-7/assets/141503408/aaff9b32-04f1-4a3a-9d9d-2c951a668915)

Apache server 2

![port 8000 server 2](https://github.com/NANA-2016/PROJECT-7/assets/141503408/2061fb9b-7f43-4f45-bbfc-3ea869e3f3d8)

 ## Step 3

 Install Apache webserver 

  These is done by installing Apache software on both servers.

   We do  nreed to comnnect each webserver to aws instance by ssh -1 <PEM KEY> ubuntu@<public ip adress of the instance >

   Apache server 1 ssh
    
![ssh apache server 1](https://github.com/NANA-2016/PROJECT-7/assets/141503408/75cb45fc-1fc5-4d4c-ab66-5a96c613ee89)
 
   Apache server 2 ssh

   ![ssh apache server 2](https://github.com/NANA-2016/PROJECT-7/assets/141503408/bf563794-21af-4360-8219-8da18a57c4b7)

    On the above screen shots you can note the difference on the <public ip addresses>.


   

   









 


