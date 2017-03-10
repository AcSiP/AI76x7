<H1> EK-AI7697H (AI7697H XBee) User Manual </H1>

<H2> Description</H2>
<BR>
EK-AI7697H, aka AI7697H XBee,  is a low-cost and easy to use Internet of Things (IoT) development platform for RTOS to design, prototype, evaluate and implement IoT projects. It is based on AI7688H stamp Module, with ARM Cortex-M4 with floating point MCU in package. The HDK enables rich connectivity features, communication with cloud services and real-time control.
<BR>

<H2> Hardware Features</H2>
<BR>
- Main Chip: MT7697N
- ARM Cortex M4 MCU with FPU with up to 192MHz clock speed
- Embedded 352KB SRAM and 64KB boot ROM
- Support 2.4G Wi-Fi IEEE 802.11 b/g/n
- Hardware crypto engines including AES, DES/3DES/ SHA2 for network security
- Internal switch and control for Rx diversity
- Bluetooth Low Energy
- Small Size 18mm X 18mm X 1.6mm
- Versatile interface:
 - 28 GPIO/PWM multiplexed with other interfaces
 - Two UART interfaces with hardware flow control and one UART for debug, all multiplexed with GPIO
 - One SPI master/slave interface multiplexed with GPIO
 - One I2S interface multiplexed with GPIO
 - Two I2C master interface multiplexed with GPIO
 - 4 channel 12-bit ADC multiplexed with GPIO
 - IrDA
<BR>
<BR>

<H2> Hardware Description</H2>
AI7687H XBee includes a main board and a AI7697H stamp module. The AI7697H stamp module is mounted on the main board.
<BR>

<H3> Top View</H3>
![PCBA Top View](EK-AI76x7_Top.jpg)
<BR>
<H3> Buttom View</H3>
![PCBA Buttom View](EK-AI7687_Bot.jpg)
<BR>

<H3> Pin Define (Top View)</H3>
![Pin Define Top View](EK-AI76x7_Top.png)
<BR>
<H3> Pin Define (Buttom View)</H3>
![Pin Define Buttom View](EK-AI76x7_Bot.png)
<BR>
<BR>

<H2> Hardware Configuration</H2>
- Setting jumpers on location [3.3V] and [GND] for supply power from USB
- Setting jumpers on location [GPIO2] and [GPIO3] for UART debug port
- Setting jumper on location [NRST] for RST key function
- BAT connector only supported 3.7V 200-1000mAh Li-ion battery
- Use Micro USB cable Connect from PC to EK-AI7697H <BR>
- Open serial console application, ex Putty or TeraTerm, with 57600 bps(8N1) <BR>
- Configuring Normal / Recovery mode
<BR>

<H2> Recovery Mode</H2>
<B>1. </B> Setting jumper on on location [CON31]<BR>
<B>2. </B> Press RST key to trigger a hardware reset. Debug console shows “ccc” always.<BR>
<BR>

Recovery mode is used for two purpose:
- RF performance test (with Mediatek QA tool)
- Update firmware (with MT76x7_Flash_Tool)
<BR>


<H2> Normal Mode</H2>
<B>1. </B> Remove jumper on on location [CON31]<BR>
<B>2. </B> Press RST key to trigger a hardware reset.<BR>
<BR>

Normal mode is the normal operation environment for user application.<BR>
Here is the example operation.<BR>
<BR>

<H3> Wi-Fi connect to an AP router (aka station mode)</H3>
- SSID of Target AP router = <B>AcSiP_Public</B>
- Pre-shared key = <B>1zx2#CV$</B>
- Auth Mode = <B>WPA2PSK</B>
- Encrypt Type = <B>AES</B>

<BR>
<B>1. </B> Change operation mode to station mode<BR>
<B>wifi config set opmode 1</B><BR>
<BR>
<B>2. </B> Set SSID<BR>
<B>wifi config set ssid 0 AcSiP_Public</B><BR>
<BR>
<B>3. </B> Configure auth information<BR>
<B>wifi config set ssid psk 0 7 8 "1zx2#CV$"</B><BR>
<BR>
The parameter definition of <B>wifi config set ask</B> list below:<BR>
wifi config set psk <B> [port] [auth mode] [encrypt type] [psk key] </B><BR>
	<TABLE>
	<TR align="center" valign="center">
		<TD><B> Combination Type </B></TD>
		<TD><B> Auth Mode </B></TD>
		<TD><B> Encrypt Type </B></TD>
	</TR>
 <TR align="center" valign="center"><TD> OPEN </TD>                    <TD> 0 </TD>	<TD> 1 </TD> </TR>
 <TR align="center" valign="center"><TD> WPA2PSK(AES) </TD>            <TD> 7 </TD>	<TD> 6 </TD> </TR>
 <TR align="center" valign="center"><TD> WPA2PSK(TKIP) </TD>           <TD> 7 </TD>	<TD> 4 </TD> </TR>
 <TR align="center" valign="center"><TD> WPA2PSK(AES+TKIP) </TD>       <TD> 7 </TD>	<TD> 8 </TD> </TR>
 <TR align="center" valign="center"><TD> WPAPSK(AES) </TD>             <TD> 4 </TD>	<TD> 6 </TD> </TR>
 <TR align="center" valign="center"><TD> WPAPSK(TKIP) </TD>            <TD> 4 </TD>	<TD> 4 </TD> </TR>
 <TR align="center" valign="center"><TD> WPAPSK+WPA2PSK(AES+TKIP) </TD><TD> 9 </TD>	<TD> 8 </TD> </TR>
 <TR align="center" valign="center"><TD> WEP(OPEN) </TD>               <TD> 0 </TD>	<TD> 0 </TD> </TR>
	</TABLE>


<BR>
<B>4. </B> Apply changes<BR>
<B>wifi config set reload</B><BR>
<BR>
<B>5. </B> Wait for few seconds, the message like below would show up if connecting to the AP successfully:<BR>
<I>[T: 5066238 M: common C: INFO F: ip_change_call_back L: 441]: ************************</I><BR>

<I>[T: 5066239 M: common C: INFO F: ip_change_call_back L: 442]: <B>DHCP got IP:</B>192.168.20.67</I><BR>

<I>[T: 5066239 M: common C: INFO F: ip_change_call_back L: 443]: ************************</I><BR>

<BR>
<B>6. </B> Get RSSI<BR>
<B>wifi connect get rssi</B><BR>
<BR>
<BR>
