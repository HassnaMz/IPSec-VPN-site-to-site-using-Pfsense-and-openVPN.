# IPSec-VPN-site-to-site-using-Pfsense-and-openVPN.
### Realized By
- [EL MAIZI HASNA](https://github.com/HassnaMz)
- [ILHAM MAHIRI](https://github.com/)
## Setting up Site To Site VPN with IPsec  
<h3 align="left">Demo:</h3>
<p align="left">
<a href="  https://youtu.be/2zq-68SIFbA" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/youtube.svg" alt=" https://youtu.be/2zq-68SIFbA " height="30" width="40" /></a>
</p>
### Technologies
Project is created with:
* PFsense
* virtuelBox

 Setting up Site To Site VPN with IPsec  
   To set it up we access the administration interface of our first Pfsense (192.168.134.29) then we go to the VPN menu > IPsec. Click on “Add P1” to edit phase 1.
   In the General Information frame the remote Pfsense IP is filled in in Remote Gateway which is here 192.168.134.28.
   
![image](https://user-images.githubusercontent.com/115992922/212722284-b9c89327-912f-4c6b-a5f0-332591856020.png)
    In the second frame we choose Mutual PSK for Authentication Method and click on Generate new Pre-Shared Key which is here to display the key.
    For the algorithm we choose AES.    
![image](https://user-images.githubusercontent.com/115992922/212724098-0c5c7c6f-ad9f-44b2-9c26-98d2dfdd6813.png)

The following is to be left by default and check the box Enable DPD.  

![image](https://user-images.githubusercontent.com/115992922/212724282-7c391d46-1c85-4455-90a6-74a7293ec4bc.png)

Then we save and click on Show Phase 2 Entries to edit phase 2.

![image](https://user-images.githubusercontent.com/115992922/212724381-66ffccb5-e8b6-440d-bf0a-c0384ff83022.png)

![image](https://user-images.githubusercontent.com/115992922/212724462-487ff5d9-1dac-45f8-85f7-19d9fe4e7c51.png)

In General Information we put the second Pfsense LAN network in Remote Network which is here 192.168.52.0/24.    
In Encryption Algorithms we choose AES (Auto) and in Hash Algorithms we choose SHA256. The rest is also left by default and then saved. 
         
![image](https://user-images.githubusercontent.com/115992922/212724682-91f89a38-982c-4825-977e-e0c142780599.png)

Then you must create rules to allow packets arriving on the PFsense WANs and via IPsec. Go to Firewall > Rules then WAN tab and put this rule  

![image](https://user-images.githubusercontent.com/115992922/212725893-7fa1ca6a-21d0-45f7-90b4-15f55aa47d7e.png)
## Setting up Site to Site VPN with IPsec using pfsense 2

In the General Information frame the remote Pfsense IP is filled in in Remote Gateway which is here 192.168.134.29.

![image](https://user-images.githubusercontent.com/115992922/212726289-b2247744-26f3-4f7a-886b-6b88ccc96c59.png)

In the second frame we choose Mutual PSK for Authentication Method and we copy the same key we used in the first configuration.

![image](https://user-images.githubusercontent.com/115992922/212726400-a6d0a511-c296-4e57-b599-3cb0a1f3bf61.png)

For the algorithm we choose AES.  

![image](https://user-images.githubusercontent.com/115992922/212726523-04de1480-c017-49bf-87a4-a4baed233ac9.png)

The following is to be left by default and the check the box Enable DPD.
  
![image](https://user-images.githubusercontent.com/115992922/212726666-eb1329f5-86a6-4c94-bacb-8852f97af913.png)
  
Then we save and click on Show Phase 2 Entries to edit phase 2

In General Information we put the LAN network of the first Pfsense in Remote Network which is here 192.168.51.0/24.  

![image](https://user-images.githubusercontent.com/115992922/212726966-fa30c35e-4b77-43ac-a5f6-701636e24d3c.png)

In Encryption Algorithms we choose AES (Auto) and in Hash Algorithms we choose SHA256. The rest is also left by default and then saved.  

Then you must create rules to allow packets arriving on the PFsense WANs and via IPsec. Go to Firewall > Rules then IPsec tab and put this rule  

![image](https://user-images.githubusercontent.com/115992922/212727195-59d26702-3bf9-4649-8fd1-8e81770571eb.png)

##	IPsec tunnel test 
Pour voir si le tunnel fonctionne il suffit de se rendre dans Status > IPsec puis   cliquer sur    Connecting, si la configuration est bonne on devrait avoir ESTABLISHED comme statut. 

![image](https://user-images.githubusercontent.com/115992922/212727619-abe70b6f-2012-4835-b19b-c98d0500fef1.png)

![image](https://user-images.githubusercontent.com/115992922/212727702-d3f33d8e-8113-46e9-bf46-65ab4ed80b1b.png)

You can also test by connecting to a LAN 1 client and pinging a LAN 2 client.   

![image](https://user-images.githubusercontent.com/115992922/212728015-f1668beb-4a3b-444b-adad-084cb67fa820.png)










 
  
   
   
    
     
     
      


     

     
    
   

   
 
  
   
   
    
     
     
      


     

     
    
   

   
 
  
   
   
    
     
     
      


     

     
    
   

   
 
  
  
   
   
   
   
   
   
   
   
   
   
   
   
  
  
  
 
  
 
  
   
   
    
     
     
      


     

     
    
   

   
 
  
   
   
    
     
     
      


     

     
    
   

   
 
  
 
  
   
   
    
     
     
      


     

     
    
   

   
 
  
   
   
    
     
     
      


     

     
    
   

   
 
  
 
  
   
   
    
     
     
      


     

     
    
   

   
 
  
   
   
    
     
     
      


     

     
    
   

   
 
  
 
  
   
   
    
     
     
      


     

     
    
   

   
 
  
   
   
    
     
     
      


     

     
    
   

   
 
  
 
  
 
 



  
