# xilinx-dphy-loopback
introduction:  
record the learing of xilinx dphy for future development of the logic analyzer   
dphy are used at csi subsystem and dsi subsystem for mamy multi-media application, so I want to develope the logic analyzer to debug its behavior.  
this is a 4 lane dphy loopback project which use dphy tx tramsmit the pattern to dphy rx  
following is the block diagram   
![alt text](https://github.com/joshuahwfwEE/xilinx-dphy-loopback/blob/main/dphy1.png?raw=true)  
base on this project it can be used in the implementation of some subsystem ip:  
for example csi/dsi tx or csi/dsi rx subsystem:  
![alt text](https://github.com/joshuahwfwEE/xilinx-dphy-loopback/blob/main/dphy.png?raw=true)  
following is dphy tx's architcture in ultrascale+:  
![alt text](https://github.com/joshuahwfwEE/xilinx-dphy-loopback/blob/main/dphytx.png?raw=true)  
following is dphy rx's architcture in ultrascale+:  
![alt text](https://github.com/joshuahwfwEE/xilinx-dphy-loopback/blob/main/dphyrx.png?raw=true)  
