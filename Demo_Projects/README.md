# Demo Projects
For AI7687H, AI7697H, AI7697HD


# Demo project 1, porting uart 2 to get data and transfer it via tcp/ip communication.
a.How to use this patch?
Please download Linkit_SDK_V4.1.0_public form https://labs.mediatek.com/en/download/AThAO9Og ,then apply it.

b.We porting simple command to demo this project,please follow these instructurtions as below.
1. Please prepare two devices.
2. Set dev1 to wifi AP mode.
    > "tcp_demo ap" command.
3. Set dev2 to wifi station mode.
    > "tcp_demo sta" command.
4. Set dev1 to tcp server and wait data form client.
    > "tcp_demo server" command.
5. Set dev2 to tcp client and got data form uart.
    > "tcp_demo client" command.
