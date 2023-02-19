The _Three-way handshake -_ the term given for the process used to establish a connection between two devices. The Three-way handshake communicates using a few special messages - the table below highlights the main ones:
<table>
    <tbody>
		<tr style="text-align:center;background-color:#063970;color:#ffffff;">
            <td style="border:2px solid #FFF"><b>Step<br></b></td>
            <td style="border:2px solid #FFF"><b>Message<br></b></td>
            <td style="border:2px solid #FFF"><b>Description<br></b></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">1<br></td>
            <td style="border:2px solid #FFF">SYN<br></td>
            <td style="border:2px solid #FFF">A SYN message is the initial packet sent by a client during the handshake. This packet is used to initiate a connection and synchronise the two devices together (we'll explain this further later on).<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">2<br></td>
            <td style="border:2px solid #FFF">SYN/ACK<br></td>
            <td style="border:2px solid #FFF">This packet is sent by the receiving device (server) to acknowledge the synchronisation attempt from the client.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">3<br></td>
            <td style="border:2px solid #FFF">ACK<br></td>
            <td style="border:2px solid #FFF">The acknowledgement packet can be used by either the client or server to acknowledge that a series of messages/packets have been successfully received.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">4<br></td>
            <td style="border:2px solid #FFF">DATA<br></td>
            <td style="border:2px solid #FFF">Once a connection has been established, data (such as bytes of a file) is sent via the "DATA" message.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">5<br></td>
            <td style="border:2px solid #FFF">FIN<br></td>
            <td style="border:2px solid #FFF">This packet is used to _cleanly (properly)_ close the connection after it has been complete.<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">#<br></td>
            <td style="border:2px solid #FFF">RST<br></td>
            <td style="border:2px solid #FFF">This packet abruptly ends all communication. This is the last resort and indicates there was some problem during the process. For example, if the service or application is not working correctly, or the system has faults such as low resources.<br></td>
        </tr>
    </tbody>
</table>

The diagram below shows a normal Three-way handshake process between Alice and Bob. In real life, this would be between two devices.
![[three-way handshake.png]]
Any sent data is given a random number sequence and is reconstructed using this number sequence and incrementing by 1. Both computers must agree on the same number sequence for data to be sent in the correct order. This order is agreed upon during three steps:

1.  SYN - Client: Here's my Initial Sequence NumberISN to **SYN**chronise with (0)
2.  SYN/ACK - Server: Here's my Initial Sequence Number (ISN) to **SYN**chronise with (5,000), and I **ACK**nowledge your initial number sequence (0)
3.  ACK - Client: I **ACK**nowledge your Initial Sequence Number (ISN) of (5,000), here is some data that is my ISN+1 (5,000 + 1)
<table>
    <tbody>
		<tr style="text-align:center;background-color:#063970;color:#ffffff;">
            <td style="border:2px solid #FFF"><b>Device<br></b></td>
            <td style="border:2px solid #FFF"><b>Initial Number Sequence (ISN)<br></b></td>
            <td style="border:2px solid #FFF"><b>Final Numer Sequence<br></b></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Client (Sender)<br></td>
            <td style="border:2px solid #FFF">0<br></td>
            <td style="border:2px solid #FFF">0 + 1 = 1<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Client (Sender)<br></td>
            <td style="border:2px solid #FFF">1<br></td>
            <td style="border:2px solid #FFF">1 + 1 = 2<br></td>
        </tr>
        <tr>
            <td style="border:2px solid #FFF">Client (Sender)<br></td>
            <td style="border:2px solid #FFF">2<br></td>
            <td style="border:2px solid #FFF">2 + 1 = 3<br></td>
        </tr>
    </tbody>
</table>

Sources : https://tryhackme.com/room/packetsframes
