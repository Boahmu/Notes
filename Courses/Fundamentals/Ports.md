Perhaps aptly titled by their name, ports are an essential point in which data can be exchanged. Think of a harbour and port. Ships wishing to dock at the harbour will have to go to a port compatible with the dimensions and the facilities located on the ship. When the ship lines up, it will connect to a **port** at the harbour. Take, for instance, that a cruise liner cannot dock at a port made for a fishing vessel and vice versa.

These ports enforce what can park and where — if it isn't compatible, it cannot park here. Networking devices also use ports to enforce strict rules when communicating with one another. When a connection has been established (recalling from the OSI model's room), any data sent or received by a device will be sent through these ports. In computing, ports are a numerical value between **0** and **65535** (65,535).

Because ports can range from anywhere between 0-65535, there quickly runs the risk of losing track of what application is using what port. A busy harbour is chaos! Thankfully, we associate applications, software and behaviours with a standard set of rules. For example, by enforcing that any web browser data is sent over port 80, software developers can design a web browser such as Google Chrome or Firefox to interpret the data the same way as one another.

This means that all web browsers now share one common rule: data is sent over port 80. How the browsers look, feel and easy to use is up to the designer or the user's decision.

While the standard rule for web data is _port 80_, a few other protocols have been allocated a standard rule. Any port that is within **0** and **1024** (1,024) is known as a common port. Let's explore some of these other protocols below:
<table>
    <tbody>
		<tr style="text-align:center;background-color:#063970;color:#ffffff;">
            <td style="border:2px solid #FFF"><b>Protocol<br></b></td>
            <td style="border:2px solid #FFF"><b>Port Number<br></b></td>
            <td style="border:2px solid #FFF"><b>Description<br></b></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">File Transfer Protocol (FTP)<br></td>
            <td style="border:2px solid #FFF">21<br></td>
            <td style="border:2px solid #FFF">This protocol is used by a file-sharing application built on a client-server model, meaning you can download files from a central location.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Secure Shell (SSH)<br></td>
            <td style="border:2px solid #FFF">22<br></td>
            <td style="border:2px solid #FFF">This protocol is used to securely login to systems via a text-based interface for management.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">HyperText Transfer Protocol (HTTP)<br></td>
            <td style="border:2px solid #FFF">80<br></td>
            <td style="border:2px solid #FFF">This protocol powers the World Wide Web (WWW)! Your browser uses this to download text, images and videos of web pages.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">HyperText Transfer Potocol Secure (HTTPS)<br></td>
            <td style="border:2px solid #FFF">443<br></td>
            <td style="border:2px solid #FFF">This protocol does the exact same as above; however, securely using encryption.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Server Message Block (SMB)<br></td>
            <td style="border:2px solid #FFF">445<br></td>
            <td style="border:2px solid #FFF">This protocol is similar to the File Transfer Protocol (FTP); however, as well as files, SMB allows you to share devices like printers.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Remote Desktop Protocol (RDP)<br></td>
            <td style="border:2px solid #FFF">3389<br></td>
            <td style="border:2px solid #FFF">This protocol is a secure means of logging in to a system using a visual desktop interface (as opposed to the text-based limitations of the SSH protocol).<br></td>
        </tr>
    </tbody>
</table>

We have only briefly covered the more common protocols in cybersecurity. You can [find a table of the 1024 common ports listed](http://www.vmaxx.net/techinfo/ports.htm) for more information.

What is worth noting here is that these protocols only follow the standards. I.e. you can administer applications that interact with these protocols on a different port other than what is the standard (running a web server on 8080 instead of the 80 standard port). Note, however, applications will presume that the standard is being followed, so you will have to provide a **colon (:)** along with the port number.

Sources : https://tryhackme.com/room/packetsframes
