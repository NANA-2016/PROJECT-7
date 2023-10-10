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

    On the above screen shots you can note the difference on the <public ip addresses> on the SSH

   'sudo apt update -y &&  sudo apt install apache2 -y'

    the command above is used to install Apache2 server on both servers on both git and git terminus as used  below. 

    Apache server 1  

   ![apache2 installation server 1](https://github.com/NANA-2016/PROJECT-7/assets/141503408/9dc74337-4c54-4c5e-9be4-10b298fef583)


   
     Apache server 2

   ![apache2 innstallation server 2](https://github.com/NANA-2016/PROJECT-7/assets/141503408/c40029f8-1def-41ad-ae16-a0a82d619300)

    After using 'sudo systemctl status apache2' to ensure Apache2 is running , we move on to the next step.

    ## Step 4
    
For both servers , we need to configure the server to port 800 hencr we add  a directive 'Listen to port 8000. as shown below using command .

 'sudo vi /etc/apache2/ports.conf '(using the nano or vi editor is ok)

 For Apache server 1 vi editor has been used
 
 ![directive addition for conf Listen 8000 server 1](https://github.com/NANA-2016/PROJECT-7/assets/141503408/b06269b2-e058-4dc1-8de1-8acc1b463713)

 For Apache server 2nano editor has been used.
 
 ![directive addition for conf Listen 8000 server 2](https://github.com/NANA-2016/PROJECT-7/assets/141503408/f407fe1a-af8d-42cd-8c1f-c4f5c1d1f8da)

  Listen 8000 on both configurations have been added as port directives 
  

   Last we need to open a default file in Apache2 server and change the default port 80 to 8000 on the virtual host after which we
   
   need to restart apache to reload the changes made .

 ![conf of port on defaul file sites available server 1](https://github.com/NANA-2016/PROJECT-7/assets/141503408/e50abcd6-b90d-4ca9-b5d6-3d9ea41b8a74)

 ![conf of port on defaul file sites available server 2](https://github.com/NANA-2016/PROJECT-7/assets/141503408/98f023d2-2376-4011-bca0-1ff0a0ed785c)

  Later a new file index.html is opened on both servers using the 'sudo vi index.html'  command 
  
  and code below where you will later       
  
  <!DOCTYPE html>
        <html>
        <head>
            <title>My EC2 Instance</title>
        </head>
        <body>
            <h1>Welcome to my EC2 instance</h1>
            <p>Public IP: YOUR_PUBLIC_IP</p>
        </body>
        </html>


  
  
  change the file ownership using 'sudo chown www-data:www-data ./index.html' command 
  
  'sudo cp -f ./index.html /var/www/html/index.html will be used to replace the default html file.
  
 and reload the apache2 load the new changes made  using 'sudo systemctl restart apache2'

  ALL THE STEPS ARE SHOWN BELOW ON EACH SERVER .

   Apache server 1

   ![configure Apache2 server  1](https://github.com/NANA-2016/PROJECT-7/assets/141503408/82561996-e633-4575-a63f-9bbd1913f8e2)

   Apache server 2

   ![configure apache2 server 2](https://github.com/NANA-2016/PROJECT-7/assets/141503408/bcd8facc-ad6f-45f9-8e23-a8f6762e01cc)

   The end result at the browser is as shown below  for both servers.

  ![web connection server 1](https://github.com/NANA-2016/PROJECT-7/assets/141503408/b0b2e1fb-2e70-472c-bda7-5dc862ac8a04)

  ![webconnection server 2](https://github.com/NANA-2016/PROJECT-7/assets/141503408/96c75b1a-73ae-46dc-9833-a99489a2fef6)


  

 


    



   


 

    
   



   


 
 


 

    

   


     

     

 

    


   

   









 


