The **U**ser **D**atagram **P**rotocol (**UDP**) is another protocol that is used to communicate data between devices.

Unlike its brother TCP, UDP is a **stateless** protocol that doesn't require a constant connection between the two devices for data to be sent. For example, the Three-way handshake does not occur, nor is there any synchronisation between the two devices.

Namely, UDP is used in situations where applications can tolerate data being lost (such as video streaming or voice chat) or in scenarios where an unstable connection is not the end-all. A table comparing the advantages and disadvantages of UDP is located below:
<table>
    <tbody>
		<tr style="text-align:center;background-color:#063970;color:#ffffff;">
            <td style="border:2px solid #FFF"><b>Advantages of UDP&nbsp;<br></b></td>
            <td style="border:2px solid #FFF"><b><span>Disadvantages of UDP</span><br></b></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF"><span>UDP is much faster than TCP. </span><br></td>
            <td style="border:2px solid #FFF"><span>UDP doesn't care if the data is received.</span><br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">UDP leaves the application layer (user software) to decide if there is any control over how quickly packets are sent.<br></td>
            <td style="border:2px solid #FFF">It is quite flexible to software developers in this sense.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">UDP does not reserve a continuous connection on a device as TCP does. <br></td>
            <td style="border:2px solid #FFF"><span>This means that unstable connections result in a terrible experience for the user. </span><br></td>
        </tr>
    </tbody>
</table>

As mentioned, no process takes place in setting up a connection between two devices. Meaning that there is no regard for whether or not data is received, and there are no safeguards such as those offered by TCP, such as data integrity.

UDP packets are much simpler than TCP packets and have fewer headers. However, both protocols share some standard headers, which are what is annotated in the table below:
<table>
    <tbody>
		<tr style="text-align:center;background-color:#063970;color:#ffffff;">
            <td style="border:2px solid #FFF"><b>Header<br></b></td>
            <td style="border:2px solid #FFF"><b><span>Description</span><br></b></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF"><span>Time to Live (TTL)</span><br></td>
            <td style="border:2px solid #FFF"><span>This field sets an expiry timer for the packet, so it doesn't clog up your network if it never manages to reach a host or escape!</span><br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Source Address<br></td>
            <td style="border:2px solid #FFF">The IP address of the device that the packet is being sent <strong>from</strong>, so that data knows where to <strong>return to</strong>.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Destination Address<br></td>
            <td style="border:2px solid #FFF"><span>The device's IP address the packet is being <strong>sent to</strong> so that data knows where to travel next.</span><br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Source Port<br></td>
            <td style="border:2px solid #FFF"><span>This value is the port that is opened by the sender to send the TCP packet from. This value is chosen randomly (out of the ports from 0-65535 that aren't already in use at the time).</span><br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Destination Port<br></td>
            <td style="border:2px solid #FFF"><span>This value is the port number that an application or service is running on the remote host (the one receiving data); for example, a webserver running on port 80. Unlike the source port, this value is not chosen at random.</span><br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Data<br></td>
            <td style="border:2px solid #FFF"><span>This header is where the data, i.e. bytes of a file that is being transmitted, is stored.</span><br></td>
        </tr>
    </tbody>
</table>


Next, we'll come on to discuss how the process of a connection via UDP differs from that of something such as TCP.  We should recall that UDP is **stateless**. No acknowledgement is sent during a connection.

The diagram below shows a normal UDP connection between Alice and Bob. In real life, this would be between two devices.
![[UDPIP-protocol.png]]

Sources : https://tryhackme.com/room/packetsframes
