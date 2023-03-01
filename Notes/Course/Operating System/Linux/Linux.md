#OS #Linux
## Where is Linux Used?
It's fair to say that Linux is a lot more intimidating to approach than Operating System's (OSs) such as Windows. Both variants have their own advantages and disadvantages. For example, Linux is considerably much more lightweight and you'd be surprised to know that there's a good chance you've used Linux in some form or another every day! Linux powers things such as:
-   Websites that you visit
-   Car entertainment/control panels
-   Point of Sale (PoS) systems such as checkout tills and registers in shops
-   Critical infrastructures such as traffic light controllers or industrial sensors

## Flavours of Linux
The name "Linux" is actually an umbrella term for multiple OS's that are based on UNIX (another operating system). Thanks to UNIX being open-source, variants of Linux comes in all shapes and sizes - suited best for what the system is being used for.
For example, Ubuntu & Debian are some of the more commonplace distributions of Linux because it is so extensible. I.e. you can run Ubuntu as a server (such as websites & web applications) or as a fully-fledged desktop. For this series, we're going to be using Ubuntu.
_Ubuntu Server can run on systems with only 512MB of RAM_

Similar to how you have different versions Windows (7, 8 and 10), there are many different versions/distributions of Linux.


## Common Directories
### /etc
This root directory is one of the most important root directories on your system. The etc folder (short for etcetera) is a commonplace location to store system files that are used by your operating system. 
For example, the sudoers file highlighted in the screenshot below contains a list of the users & groups that have permission to run sudo or a set of commands as the root user.
Also highlighted below are the "**passwd**" and "**shadow**" files. These two files are special for Linux as they show how your system stores the passwords for each user in encrypted formatting called sha512.

### /var 
The "/var" directory, with "var" being short for variable data,  is one of the main root folders found on a Linux install. This folder stores data that is frequently accessed or written by services or applications running on the system. For example, log files from running services and applications are written here (**/var/log**), or other data that is not necessarily associated with a specific user (i.e., databases and the like).

### /root
Unlike the **/home** directory, the **/root** folder is actually the home for the "root" system user. There isn't anything more to this folder other than just understanding that this is the home directory for the "root" user. But, it is worth a mention as the logical presumption is that this user would have their data in a directory such as "**/home/root**" by default.

### /tmp
This is a unique root directory found on a Linux install. Short for "temporary", the /tmp directory is volatile and is used to store data that is only needed to be accessed once or twice. Similar to the memory on your computer, once the computer is restarted, the contents of this folder are cleared out.
What's useful for us in pentesting is that any user can write to this folder by default. Meaning once we have access to a machine, it serves as a good place to store things like our enumeration scripts.

## How do Processes Start?
Let's start off by talking about namespaces. The Operating System (OS) uses namespaces to ultimately split up the resources available on the computer to (such as CPU, RAM and priority) processes. Think of it as splitting your computer up into slices -- similar to a cake. Processes within that slice will have access to a certain amount of computing power, however, it will be a small portion of what is actually available to every process overall.

Namespaces are great for security as it is a way of isolating processes from another -- only those that are in the same namespace will be able to see each other.

We previously talked about how PID works, and this is where it comes into play. The process with an ID of 0 is a process that is started when the system boots. This process is the system's init on Ubuntu, such as **systemd**, which is used to provide a way of managing a user's processes and sits in between the operating system and the user. 

For example, once a system boots and it initialises, **systemd** is one of the first processes that are started. Any program or piece of software that we want to start will start as what's known as a child process of **systemd**. This means that it is controlled by **systemd**, but will run as its own process (although sharing the resources from **systemd**) to make it easier for us to identify and the likes.
![[linux-pid.png]]

## Getting Processes/Services to Start on Boot
Some applications can be started on the boot of the system that we own. For example, web servers, database servers or file transfer servers. This software is often critical and is often told to start during the boot-up of the system by administrators.
In this example, we're going to be telling the apache web server to be starting apache manually and then telling the system to launch apache2 on boot.
Enter the use of `systemctl` -- this command allows us to interact with the **systemd** process/daemon. Continuing on with our example, systemctl is an easy to use command that takes the following formatting: `systemctl [option] [service]`
For example, to tell apache to start up, we'll use `systemctl start apache2`. Seems simple enough, right? Same with if we wanted to stop apache, we'd just replace the `[option]` with stop (instead of start like we provided)

We can do four options with `systemctl`:
-   Start
-   Stop
-   Enable
-   Disable

## An Introduction to Backgrounding andForegrounding in Linux
Processes can run in two states: In the background and in the foreground. For example, commands that you run in your terminal such as "echo" or things of that sort will run in the foreground of your terminal as it is the only command provided that hasn't been told to run in the background. "Echo" is a great example as the output of echo will return to you in the foreground, but wouldn't in the background - take the screenshot below, for example.
![[backgroundingForegrounding1.png]]
Here we're running `echo "Hi THM"` , where we expect the output to be returned to us like it is at the start. But after adding the `&` operator to the command, we're instead just given the ID of the echo process rather than the actual output -- as it is running in the background.
This is great for commands such as copying files because it means that we can run the command in the background and continue on with whatever further commands we wish to execute (without having to wait for the file copy to finish first)
We can do the exact same when executing things like scripts -- rather than relying on the & operator, we can use `Ctrl + Z` on our keyboard to background a process. It is also an effective way of "pausing" the execution of a script or command like in the example below:
![[backgroundingForegrounding2.png]]
This script will keep on repeating "This will keep on looping until I stop!" until I stop or suspend the process. By using `Ctrl + Z` (as indicated by **T^Z**). Now our terminal is no longer filled up with messages -- until we foreground it, which we will discuss below.

### Foregrounding a process
Now that we have a process running in the background, for example, our script "background.sh" which can be confirmed by using the `ps aux`command, we can back-pedal and bring this process back to the foreground to interact with.
![[backgroundingForegrounding3.png]]
With our process backgrounded using either `Ctrl + Z` or the `&` operator, we can use `fg` to bring this back to focus like below, where we can see the `fg` command is being used to bring the background process back into use on the terminal, where the output of the script is now returned to us.
![[Sources/Pictures/Operating System/Linux/backgroundingForegrounding4.png]]
![[backgroundingForegrounding4 1.png]]

## Maintaining Your System: Automation
Users may want to schedule a certain action or task to take place after the system has booted. Take, for example, running commands, backing up files, or launching your favourite programs on, such as Spotify or Google Chrome.  

We're going to be talking about the `cron` process, but more specifically, how we can interact with it via the use of `crontabs` . Crontab is one of the processes that is started during boot, which is responsible for facilitating and managing cron jobs.
![[automation.png]]
A crontab is simply a special file with formatting that is recognised by the `cron` process to execute each line step-by-step. Crontabs require 6 specific values:
<table>
    <tbody>
		<tr style="text-align:center;background-color:#063970;color:#ffffff;">
            <td style="border:2px solid #FFF"><b>Value<br></b></td>
            <td style="border:2px solid #FFF"><b>Description<br></b></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">MIN<br></td>
            <td style="border:2px solid #FFF">What minute to execute at<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">HOUR<br></td>
            <td style="border:2px solid #FFF">What hour to execute at<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">DOM<br></td>
            <td style="border:2px solid #FFF">What day of the month to execute at<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">MON<br></td>
            <td style="border:2px solid #FFF">What month of the year to execute at<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">DOW<br></td>
            <td style="border:2px solid #FFF">What day of the week to execute at<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">CMD<br></td>
            <td style="border:2px solid #FFF">The actuel command that will be executed<br></td>
        </tr>
    </tbody>
</table>
Let's use the example of backing up files. You may wish to backup "cmnatic"'s  "Documents" every 12 hours. We would use the following formatting:
```shell
0 *12 * * * cp -R /home/cmnatic/Documents /var/backups/`
```
An interesting feature of crontabs is that these also support the wildcard or asterisk (`*`). If we do not wish to provide a value for that specific field, i.e. we don't care what month, day, or year it is executed -- only that it is executed every 12 hours, we simply just place an asterisk.

This can be confusing to begin with, which is why there are some great resources such as the online "[Crontab Generator](https://crontab-generator.org/)" that allows you to use a friendly application to generate your formatting for you! As well as the site "[Cron Guru](https://crontab.guru/)"!

Crontabs can be edited by using `crontab -e`, where you can select an editor (such as Nano) to edit your crontab.
![[crowntab1.png]]
![[crowntab2.png]]

## Maintaining Your System: Package Management
### Introducing Packages & Software Repos
When developers wish to submit software to the community, they will submit it to an  "apt" repository. If approved, their programs and tools will be released into the wild. Two of the most redeeming features of Linux shine to light here: User accessibility and the merit of open source tools.

When using the`ls`command on a Ubuntu 20.04 Linux machine, these files serve as the gateway/registry.
![[PM1.png]]
![[PM2.png]]
Whilst Operating System vendors will maintain their own repositories, you can also add community repositories to your list! This allows you to extend the capabilities of your OS. Additional repositories can be added by using the `add-apt-repository`command or by listing another provider! For example, some vendors will have a repository that is closer to their geographical location.

### Managing Your Repositories (Adding and Removing)
Normally we use the apt command to install software onto our Ubuntu system. The `apt` command is a part of the package management software also named apt. Apt contains a whole suite of tools that allows us to manage the packages and sources of our software, and to install or remove software at the same time.

One method of adding repositories is to use the `add-apt-repository` command we illustrated above, but we're going to walk through adding and removing a repository manually. Whilst you can install software through the use of package installers such as `dpkg`, the benefits of apt means that whenever we update our system -- the repository that contains the pieces of software that we add also gets checked for updates. 

In this example, we're going to add the text editor Sublime Text to our Ubuntu machine as a repository as it is not a part of the default Ubuntu repositories. When adding software, the integrity of what we download is guaranteed by the use of what is called GPG (Gnu Privacy Guard) keys. These keys are essentially a safety check from the developers saying, "here's our software". If the keys do not match up to what your system trusts and what the developers used, then the software will not be downloaded.

So, to start, we need to add the GPG key for the developers of Sublime Text 3. (Note that TryHackMe instances do not have internet access and so we're not expecting you to add this to the machine that you deploy, as it would fail.)

**1.** Let's download the GPG key and use apt-key to trust it:  `wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -`

**2.** Now that we have added this key to our trusted list, we can now add Sublime Text 3's repository to our apt sources list. A good practice is to have a separate file for every different community/3rd party repository that we add.

**2.1.** Let's create a file named **sublime-text.list** in **/etc/apt/sources.list.d** and enter the repository information like so:
![[PM3.png]]
**2.2.** And now use Nano or a text editor of your choice to add & save the Sublime Text 3 repository into this newly created file:
![[PM4.png]]
**2.3.** After we have added this entry, we need to update apt to recognise this new entry -- this is done using the `apt update` command

**2.4.** Once successfully updated, we can now proceed to install the software that we have trusted and added to apt using `apt install sublime-text`

Removing packages is as easy as reversing. This process is done by using the `add-apt-repository --remove ppa:PPA_Name/ppa` command or by manually deleting the file that we previously added to. Once removed, we can just use `apt remove [software-name-here]` i.e. `apt remove sublime-text`

## Maintaining Your System : Logs
We briefly touched upon log files and where they can be found in Linux Fundamentals Part 1. However, let's quickly recap. Located in the /var/log directory, these files and folders contain logging information for applications and services running on your system. The Operating System  (OS) has become pretty good at automatically managing these logs in a process that is known as "rotating".

I have highlighted some logs from three services running on a Ubuntu machine:

-   An Apache2 web server
-   Logs for the fail2ban service, which is used to monitor attempted brute forces, for example
-   The UFW service which is used as a firewall

![[logs1.png]]

These services and logs are a great way in monitoring the health of your system and protecting it. Not only that, but the logs for services such as a web server contain information about every single request - allowing developers or administrators to diagnose performance issues or investigate an intruder's activity. For example, the two types of log files below that are of interest:
-   access log
-   error log

![[logs2.png]]
There are, of course, logs that store information about how the OS is running itself and actions that are performed by users, such as authentication attempts.




Sources : 
https://tryhackme.com/room/linuxfundamentalspart3
https://tryhackme.com/room/linuxfundamentalspart2
https://tryhackme.com/room/linuxfundamentalspart1