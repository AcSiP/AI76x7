#1.How to use this patch?
###a.Please download Linkit_SDK_V4.1.0_public form https://labs.mediatek.com/en/download/AThAO9Og  
###b.Apply it!
___
#2.We porting simple command to demo this project,please follow these instructurtions as below.
###a.Please prepare two devices.
###b.Use "tcp_demo ap" to set DEV1 to AP mode.
![alt text](https://github.com/AcSiP/AI76x7/blob/master/Demo_Projects/Wi-Fi%20UART%20Demo/tcp_demo_ap.png "tcp_demo ap")
###c.Use "tcp_demo sta" to set DEV2 to STA mode,and connect to DEV1
![alt text](https://github.com/AcSiP/AI76x7/blob/master/Demo_Projects/Wi-Fi%20UART%20Demo/tcp_demo_sta.png "tcp_demo sta")
###d.Run "tcp_demo server" on DEV1.
![alt text](https://github.com/AcSiP/AI76x7/blob/master/Demo_Projects/Wi-Fi%20UART%20Demo/tcp_demo_server.png "tcp_demo server")
###e.Run "tcp_demo client" to create a connection.
![alt text](https://github.com/AcSiP/AI76x7/blob/master/Demo_Projects/Wi-Fi%20UART%20Demo/tcp_client_1.png "tcp_demo client")
###f.Input data form DEV2 UART and transfer it to DEV1.
![alt text](https://github.com/AcSiP/AI76x7/blob/master/Demo_Projects/Wi-Fi%20UART%20Demo/tcp_demo_client.png "tcp_demo client")
