#Fundamental 
A **V**irtual **P**rivate **N**etwork (or **VPN** for short) is a technology that allows devices on separate networks to communicate securely by creating a dedicated path between each other over the Internet (known as a tunnel). Devices connected within this tunnel form their own private network.

For example, only devices within the same network (such as within a business) can directly communicate. However, a VPN allows two offices to be connected. Let's take the diagram below, where there are three networks:
![[VPN.png]]

1.  Network #1 (Office #1)
2.  Network #2 (Office #2)
3.  Network #3 (Two devices connected via a VPN)

The devices connected on Network #3 are still a part of Network #1 and Network #2 but also form together to create a private network (Network #3) that only devices that are connected via this VPN can communicate over.

  
Let's cover some of the other benefits offered by a VPN in the table below:
<table>
    <tbody>
		<tr style="text-align:center;background-color:#063970;color:#ffffff;">
            <td style="border:2px solid #FFF"><b>Benefit<br></b></td>
            <td style="border:2px solid #FFF"><b><span>Description</span><br></b></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF"><span>Allows networks in different geographical locations to be connected.</span><br></td>
            <td style="border:2px solid #FFF"><span>For example, a business with multiple offices will find VPNs beneficial, as it means that resources like servers/infrastructure can be accessed from another office.</span><br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Offers privacy.<br></td>
            <td style="border:2px solid #FFF">VPN technology uses encryption to protect data. This means that it can only be understood between the devices it was being sent from and is destined for, meaning the data isn't vulnerable to sniffing.<br><br>This encryption is useful in places with public WiFi, where no encryption provided by the network. You can use a VPN to protect your traffic from being viewed by other people.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Offers anonyminity.<br></td>
            <td style="border:2px solid #FFF"><span>Journalists and activists depend upon VPNs to safely report on global issues in countries where freedom of speech is controlled.<br><br>Usually, your traffic can be viewed by your ISP and other intermediaries and therefore tracked. <br><br>The level of anonymity a VPN provides is only as much as how other devices on the network respect privacy.. For example, a VPN that logs all of your data/history is essentially the same as not using a VPN in this regard.</span><br></td>
        </tr>
    </tbody>
</table>

VPN technology has improved over the years. Let's explore some existing VPN technologies below:
<table>
    <tbody>
		<tr style="text-align:center;background-color:#063970;color:#ffffff;">
            <td style="border:2px solid #FFF"><b>VPN Technology<br></b></td>
            <td style="border:2px solid #FFF"><b><span>Description</span><br></b></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF"><span>PPP</span><br></td>
            <td style="border:2px solid #FFF"><span>This technology is used by PPTP (explained below) to allow for authentication and provide encryption of data. VPNs work by using a private key and public certificate (similar to <strong>SSH</strong>). A private key and certificate must match for you to connect.<br>This technology is not capable of leaving a network by itself (non-routable).</span><br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">PPTP<br></td>
            <td style="border:2px solid #FFF">The Point-to-Point Tunneling Protocol (<strong>PPTP</strong>) is the technology that allows the data from PPP to travel and leave a network. <br><br>PPTP is very easy to set up and is supported by most devices. It is, however, weakly encrypted in comparison to alternatives.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">IPSec<br></td>
            <td style="border:2px solid #FFF"><span>Internet Protocol Security (IPsec) encrypts data using the existing Internet Protocol (<strong>IP</strong>) framework.<br><br>IPSec is difficult to set up in comparison to alternatives; however, if successful, it boasts strong encryption and is also supported on many devices.</span><br></td>
        </tr>
    </tbody>
</table>

Sources : https://tryhackme.com/room/extendingyournetwork
