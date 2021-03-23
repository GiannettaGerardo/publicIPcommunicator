# publicIPcommunicator
This program is useful for those who need a static public IP address for a server but do not have one available, so it allows you to always have the dynamic public IP address available wherever you are, by e-mail. Communicate the public IP address of the computer on which the program is running by sending an e-mail wherever you want. It remains listening for connection, when the connection is lost or the router/modem is restarted, the program finds the "new" public IP address and sends it back.
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

*The use of a Gmail is recommended.
*It will be mandatory to allow access to Google via "unsecured" apps, via account settings. 
*Therefore it is recommended to create a new account specifically dedicated to this function.
