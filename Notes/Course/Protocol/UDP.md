#Protocol 
The **U**ser **D**atagram **P**rotocol (**UDP** for short). This protocol is not nearly as advanced as its brother - the TCP protocol. It doesn't boast the many features offered by TCP, such as error checking and reliability. In fact, any data that gets sent via UDP is sent to the computer whether it gets there or not. There is no synchronisation between the two devices or guarantee; just hope for the best, and fingers crossed.

Whilst this sounds disadvantageous, it does have its merits, which we'll layout in the table below:
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


Using the same example as TCP courses, we can now see that only Packets #1 and #3 have been received by the "Computer", meaning that half of the image is missing.  

![[UDP-protocol.png]]

UDP is useful in situations where there are small pieces of data being sent. For example, protocols used for discovering devices (ARP and DHCP) or larger files such as video streaming (where it is okay if some part of the video is pixelated. Pixels are just lost pieces of data!)

Sources : https://tryhackme.com/room/osimodelzi
