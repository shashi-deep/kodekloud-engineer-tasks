#### 1Q-During the daily standup, it was pointed out that the timezone across Nautilus Application Servers in Stratos Datacenter doesn't match with that of the local datacenter's timezone, which is America/Lower_Princes.

1A -
```
Ans:
To set the timezone in Linux, update /etc/localtime with the appropriate timezone file from /usr/share/zoneinfo. 
Example:
rm -f /etc/localtime
ln -sf /usr/share/zoneinfo/America/Los_Angeles /etc/localtime

This would set your time zone to PST/PDT (Pacific Time) because that is the time zone Los Angles is located in.

Or 

sudo timedatectl set-timezone America/Lower_Princes


```


#### 2Q - The System admin team of xFusionCorp Industries has installed a backup agent tool on all app servers. As per the tool's requirements they need to create a user with a non-interactive shell.Therefore, create a user named siva with a non-interactive shell on the App Server 3

2A - 

```
id shiva (to check if user exist)
adduser siva  -s /sbin/nologin ( create a user with non interactive shell )
cat /etc/passwd |grep shiva ( check if user exist)

```

#### 3Q - Install the required packages of SElinux on App server 2 in Stratos Datacenter and disable it permanently for now; it will be enabled after making some required configuration changes on this host. Don't worry about rebooting the server as there is already a reboot scheduled for tonight's maintenance window. Also ignore the status of SElinux command line right now; the final status after reboot should be disabled.


3A -

```
sudo yum install policycoreutils policycoreutils-python selinux-policy selinux-policy-targeted libselinux-utils setroubleshoot-server setools setools-console mcstrans

https://www.digitalocean.com/community/tutorials/an-introduction-to-selinux-on-centos-7-part-1-basic-concepts


```


#### 4Q - On all App servers in Stratos Datacenter change the default runlevel so that they can boot in GUI (graphical user interface)

4A -

```

# Check the defaut run level     

      systemctl get-default

#Check the graphical.target status 

    systemctl status graphical.target

#Now let set the run level to graphical.target 

    systemctl set-default graphical.target

#start and enable  the graphical.target

    systemctl start graphical.target

    systemctl enable graphical.target

#Now lets check the status again 

    systemctl status graphical.target

    systemctl get-default
```


#### 5Q- a. Delete all lines containing word copyright and save results in /home/BSD_DELETE.txt file. (Please be aware of case sensitivity)

b. Replace all occurrence of word from to them and save results in /home/BSD_REPLACE.txt file.

Note: Let's say you are asked to replace word to with from. In that case, make sure not to alter any words containing this string; for example upto, contributor etc.

5A -

```
sed '/\<copyright\>/d' /home/BSD.txt > /home/BSD_DELETE.txt

sed 's/\bfrom\b/them/g' /home/BSD.txt > /home/BSD_REPLACE.txt

```






