# Host-Website-On-Azure-Windows-VM 

<h1>Host Website using Azure - Prerequisites and Installation</h1>
This tutorial outlines the setting up of a website on Azure and Azure services .<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure Virtual Machine
- Microsoft Azure (Virtual Machines/Compute)
- Linux Virtual Machines
- Storage Account
- App Service 


<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)
- Windows Server 2022 


<h2> Installation Steps </h2>  

<h2> Create Resources Group and Virtual Machines on Azure </h2>  

<br />
<p>
	- First, create a Resource Group
</p>
<p>
	Name my resource group Test-RG
</p>  
 <img src= "https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/b2efd003-bc5c-48d5-ade5-562b6ccd80a5"/>

<p>
(1) -	Create a Windows 10 Virtual Machine 
(2) - Set image to Windows Server 2022 DataCenter 
(3)- Allow Run with Azure Spot Discount 
(4) - Use standard 2 cores for VM size 
(5) - Create username/pwd 

</p>
<p>
         <img src="https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/6ee81005-14cb-4656-8811-2fe698763c8d"/>

</p>

<p>
    Before completing the creation of the VM, go to the Monitoring tab and disable Boot Diagnostics then Review and Create VM 
</p> 
<p>
    <img src="https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/8aa203bc-011c-43f3-a2ab-921ba2fb6da6"/>
</p> 
<p>
  <img src= "https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/0968aa3c-bd98-47c1-a4f1-05478f1f8e33"/>
</p>

<br /> 
<br />
<h3> Connect to your Virtual Machine with Remote Desktop</h3>
<br />
<p>
	-If using PC, use Remote Desktop Connection
        
</p>
<p> 
      -If using a Mac, use Microsoft Remote Desktop
</p> 

<p>  
      -Use the VM public IP address to connect, along with the username and password that you used when VM was created.
</p>
	
<p>
	<img src="https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/5cbbc588-b4ce-4fcb-b95b-87cad6e24643"/>
</p>
<br />
<br />
<h3>  Add Inbound Rule </h3>
<br />
<p>
      -Back in Azure portal, go to Network Setting in Windows Virtual Machine go to Create Port Rule, and add Inbound Port Rule
</p>	
<p> 
     -On the Inbound Port Rule page, change the Destination port range to 80 which is HTTP, this serves as the communication gateway for HTTP requests and responses
</p> 
<p>
    -Change the name of the Inbound Rule to something more suitable to the rule, I changed the name to Allow_HTTP 
</p> 
<p>
    <img src= "https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/68e12d7a-c306-43ee-818b-17ced5a00ad1"/>
</p>
<br />
<h3>  Add and install Web Server (IIS) </h3>
<br />
 <p>
     -Go to the search bar and find Windows features on and off 
 </p>
 <p>
   <img src="https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/6361f2b3-2fdb-4676-8a84-bcc835e73f9b"/> 
 </p> 
<p>
    -You will be directed to Add Roles and Wizards Page and click next, choose Role-based, and click next for Server Selection
</p>
<p>
     <img src="https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/24dc7c71-6fbf-43f9-9379-db3fae3778be"/>
</p>  
<p>
    -When you reach Server Roles, check Web Server (IIS) and add features 
     
</p>
   
<p>
	 <img src="https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/6d73cd81-9e89-4de3-9fd8-3efdf0d35367"/> 
</p>  

<p>
   -Click next to the following features and press install 
</p>
<p>
  <img src= "https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/2630233f-c2ff-4021-b69f-04e9fe257e02"/> 
</p> 
<p>
  - After installing, go check in a web browser enter the IP address of the VM, and see if Internet Information Services show up
</p> 
<p>

<img src= "https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/dff32885-7678-4665-be40-c812a5af6e0c"/>
</p>  
<br />
<br />
<h3>  Host the Website </h3>
<br />
<p>
     You can go to the VM and Go to https://github.com/learning-zone/website-templates for a free open-source HTML website template for our foundation.  
 </p>
<p>
  <img src="https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/f0feaf93-8557-484f-aa83-2fb6103da409" /> 
</p> 
<p>
  - Go ahead and download the zip file of the website templates 
</p>
<p>
  <img src= "https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/68fcc107-fea2-48b7-8fa1-41b436eaaea7"/>
</p> 
<p>
  -You can choose any website template file as you please, and you will extract it or copy the files in it
</p>

<p>
  <img src="https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/45a6eba9-fde0-491a-8b7e-805d8f9c99ef" />
</p> 

<p>
   - I choose to copy the contents from a John Doe Resume portfolio template file
</p> 
<p>
   <img src= "https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/7fb080b7-605f-4daa-9bd4-8081b6b4920b"/>

</p>   
<p>
     -After copy, go to This PC --> Windows C: ---> inetpub file ---> wwwroot

</p>
  
<p>   
   <img src="https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/325d3f9f-358f-4f43-acfe-e411ae609e68"/>
</p>  
<p>
   -Delete the contents of wwwroot and download the copied files to wwwroot 
</p>
<p>
   <img src="https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/faa7b08b-f5f4-4a7c-a63b-2a2e70d19bec"/>
</p> 

<p>
   -Go back to the web browser and enter the IP address of the VM and see the website content is John Doe Portfolio 
</p>
<p>
  <img src="https://github.com/ethansevilla/Host-Website-On-Azure/assets/170621372/6937c8ca-6f1b-4bc7-9cb1-deedee5a215c"/>
</p> 

