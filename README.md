# publicIPcommunicator
This program is useful for those who need a static public IP address for a server but do not have one available, so it allows you to always have the dynamic public IP address available wherever you are, by e-mail. Communicate the public IP address of the computer on which the program is running by sending an e-mail wherever you want. It remains listening for connection, when the connection is lost or the router/modem is restarted, the program finds the "new" public IP address and sends it back.
******************************************************************************
I personally wrote and use this program to run it on a Raspberry Pi 4 device with Ubuntu Server installed. The Raspberry is located in my house, connected to the router via an ethernet cable. Not having a static public IP address for this server, I opted for a DIY solution. Wherever I am, I always have access to my server; if my router were to reboot or have problems for a while, the public IP address might change being dynamic. This problem no longer occurs with this program, in fact as soon as the connection is re-established, the new public IP address will be sent to me by e-mail.
******************************************************************************
SSMTP CONFIGURATION:

     sudo apt install ssmtp -y
     sudo su #you need root privileges
     cd /etc/ssmtp
     nano ssmtp.conf
******************************************************************************
Configure the file like this:

     #root=postmaster
     SERVER=email
     mailhub=smtp.gmail.com:587
     AuthUser=email
     AuthPass=password
     UseTLS=YES
     UseSTARTTLS=YES
     rewriteDomain=gmail.com
     hostname=#use the command hostname to get your hostname to write here
     FromLineOverride=YES
******************************************************************************
Recommendations:

For the configuration of ssmtp program, the use of a Gmail is recommended.

It will be mandatory to allow access to Google via "unsecured" apps, via account settings. 

Therefore it is recommended to create a new account specifically dedicated to this function.
