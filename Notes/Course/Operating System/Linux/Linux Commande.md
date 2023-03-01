#Linux #Commande
## General
#### echo
```shell 
# Output any text that we provide
echo "test"
```

#### whoami
```shell 
# Find out what user we're currently logged in as!
whoami
```


## Filesystem
#### touch
```shell 
# create file
touch test.txt
```

#### mkdir
```shell 
# create folder
ls test
```

#### cp
```shell 
# copy a file or folder
ls note noteBis
```

#### mv
```shell 
# move a file or folder
ls note \home\noteBis
```

#### rm
```shell 
# remove a file or folder
rm note.txt
```

#### file
```shell 
# determine the type of a file
file note
```

#### ls
```shell 
# listing
ls
```

#### cd
```shell 
# change directory
cd /DirectorToswitch/
# back in previous directory
cd ..
# back in 2 previous directory
cd ../..
```

#### cat
```shell 
# concatenate
cat nomDuFichier.txt
```

#### pwd
print working directory
```shell 
# print working directory
pwd
```

#### find
```shell 
# Using "find" to find a file with the name of "file.txt"
find -name file.txt
# Using "find" to find any file with the extension of ".txt"
find -name *.txt
```

#### wc
```shell 
# Using "wc" to count the number of entries in "access.log"
wc -l acces.log
```

#### grep
```shell 
# Using "grep" to find any entries with the IP address of "81.143.211.90" in "access.log"
grep "81.143.211.90" access.log
```


## Operator
<table>
    <tbody>
		<tr style="text-align:center;background-color:#063970;color:#ffffff;">
            <td style="border:2px solid #FFF"><b>Symbol / Operator<br></b></td>
            <td style="border:2px solid #FFF"><b>Description<br></b></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">&<br></td>
            <td style="border:2px solid #FFF">This operator allows you to run commands in the background of your terminal.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">&&<br></td>
            <td style="border:2px solid #FFF">This operator allows you to combine multiple commands together in one line of your terminal.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">><br></td>
            <td style="border:2px solid #FFF">This operator is a redirector - meaning that we can take the output from a command (such as using cat to output a file) and direct it elsewhere.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">>><br></td>
            <td style="border:2px solid #FFF">This operator does the same function of the `>` operator but appends the output rather than replacing (meaning nothing is overwritten).<br></td>
        </tr>
    </tbody>
</table>


## General/Useful Utilities
#### wget 
```shell 
# downloading files
wget https://assets.tryhackme.com/additional/linux-fundamentals/part3/myfile.txt
```

#### scp
```shell
# Transferring Files From Your Host
# scp 
# 1- Name of the file on the local system
# 2- User on the remote system
# 3- The IP address of the remote system
# 4- Name that we wish to store the file as on the remote system
scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt
```

#### start a web server
```shell
# Using Python to start a web server
python3 -m http.server
# now u can download a file from our webserver using wget
```

## Process
### Viewing processes
#### ps
```shell
# provide a list of the running processes as our user's session
ps
# To see the processes run by other users and those that don't run from a session
ps aux
```

#### top 
```shell
# top gives you real-time statistics about the processes running on your system instead of a one-time view.
top
```


### Managing processes
#### kill
```shell
#Below are some of the signals that we can send to a process when it is killed:
# SIGTERM - Kill the process, but allow it to do some cleanup tasks beforehand
# SIGKILL - Kill the process - doesn't do any cleanup after the fact
# SIGSTOP - Stop/suspend a process
kill
```

#### systemctl
```shell 
# Getting Processes/Services to Start on Boot
# We can do four options with `systemctl`:
# Start / Stop / Enable / Disable
systemctl start apache2
```

## Terminal text editors
#### nano
```shell 
nano file.txt
```



























Sources : 
https://tryhackme.com/room/linuxfundamentalspart3
https://tryhackme.com/room/linuxfundamentalspart2
https://tryhackme.com/room/linuxfundamentalspart1