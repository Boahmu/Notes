#Fundamental 

A firewall is a device within a network responsible for determining what traffic is allowed to enter and exit. Think of a firewall as border security for a network. An administrator can configure a firewall to **permit** or **deny** traffic from entering or exiting a network based on numerous factors such as:

-   Where the traffic is coming from? (has the firewall been told to accept/deny traffic from a specific network?)
-   Where is the traffic going to? (has the firewall been told to accept/deny traffic destined for a specific network?)
-   What port is the traffic for? (has the firewall been told to accept/deny traffic destined for port 80 only?)
-   What protocol is the traffic using? (has the firewall been told to accept/deny traffic that is UDP, TCP or both?)

Firewalls perform packet inspection to determine the answers to these questions.

Firewalls come in all shapes and sizes. From dedicated pieces of hardware (often found in large networks like businesses) that can handle a magnitude of data to residential routers (like at your home!) or software such as [Snort](https://www.snort.org/), firewalls can be categorised into 2 to 5 categories.

We'll cover the two primary categories of firewalls in the table below:
<table>
    <tbody>
		<tr style="text-align:center;background-color:#063970;color:#ffffff;">
            <td style="border:2px solid #FFF"><b>Firewall Category<br></b></td>
             <td style="border:2px solid #FFF"><b>Description<br></b></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Stateful<br></td>
            <td style="border:2px solid #FFF">This type of firewall uses the entire information from a connection; rather than inspecting an individual packet, this firewall determines the behaviour of a device <strong>based upon the entire connection.</strong><br><br>
			This firewall type consumes many resources in comparison to stateless firewalls as the decision making is dynamic. For example, a firewall could allow the first parts of a TCP handshake that would later fail.<br><br>
			If a connection from a host is bad, it will block the entire device.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Stateless<br></td>
            <td style="border:2px solid #FFF">This firewall type uses a static set of rules to determine whether or not <strong>individual packets</strong> are acceptable or not. For example, a device sending a bad packet will not necessarily mean that the entire device is then blocked.<br><br>Whilst these firewalls use much fewer resources than alternatives, they are much dumber. For example, these firewalls are only effective as the rules that are defined within them. If a rule is not exactly matched, it is effectively useless.<br><br>However, these firewalls are great when receiving large amounts of traffic from a set of hosts (such as a Distributed Denial-of-Service attack)<br></td>
        </tr>
    </tbody>
</table>
