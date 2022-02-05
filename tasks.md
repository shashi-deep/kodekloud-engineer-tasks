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
