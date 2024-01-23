# xilinx-dphy-loopback
story: 
record the learing of xilinx dphy for development of the other application 
dphy are used at csi subsystem and dsi subsystem for mamy multi-media application, so I want to develope the logic analyzer to debug its behavior.  
this is a 4 lane dphy loopback project which use dphy tx tramsmit the pattern to dphy rx 
the mipi_dphy_frm_gen in tx side will generate the PPI signal to control the dphy lanes seperately and mipi_dphy_frm_chk in rx side will restore the mipi sigal into PPI signal and vaildate the behavior 
following is the dphy loopback block diagram   
![alt text](https://github.com/joshuahwfwEE/xilinx-dphy-loopback/blob/main/bd1.png?raw=true)  
base on this project it can be used in the implementation of some subsystem ip: for example csi/dsi tx or csi/dsi rx subsystem:  
following is dphy tx's architcture in ultrascale+:  
![alt text](https://github.com/joshuahwfwEE/xilinx-dphy-loopback/blob/main/dphytx.png?raw=true)  
following is dphy rx's architcture in ultrascale+:  
![alt text](https://github.com/joshuahwfwEE/xilinx-dphy-loopback/blob/main/dphyrx.png?raw=true)  

intrduction of dphy:  
D-PHY describes a source synchronous, high speed, low power, low cost PHY  
A PHY configuration contains A Clock Lane One or more Data Lanes  
Three main lane types: Unidirectional Clock Lane, Unidirectional Data Lane, Bi-directional Data Lane  
Transmission Mode: Low-Power signaling mode for control purpose：10MHz (max)  
High-Speed signaling mode for fast-data traffic：80Mbps ~ 1Gbps  
per Lane D-PHY low-level protocol specifies a minimum data unit of one byte  
A transmitter shall send data LSB first, MSB last.  
D-PHY suited for mobile applications:  
DSI：Display Serial Interface A clock lane, One to four data lanes.  
CSI：Camera Serial Interface A clock lane, One to four data lanes.  

a typically dphy lane module should contain:  
Low-Power Transmitter (LP-TX)  
Low-Power Receiver (LP-RX)  
High-Speed Transmitter (HS-TX)  
High-Speed Receiver (HS-RX)  
Low-Power Contention Detector (LP-CD)  
Three main lane types:  

Unidirectional Clock Lane:  
Master HS-TX, LP-TX  
Slave：HS-RX, LP-RX    

Unidirectional Data Lane:  

Bi-directional Data Lane:  
Master: HS-TX, HS-RX   
Slave： LP-TX, LP-RX, LP-CD  


4 Low-Power Lane states (LP-00, LP-01, LP-10, LP-11)  
2 High Speed Lane states (HS-0, HS-1)  

Escape: Escape mode request (LP-11→LP-10→LP-00→LP-01→LP-00)  
Burst:  High-Speed mode request (LP-11→LP-01→LP-00)  
control: Turnaround request (LP-11→LP-10→LP-00→LP-10→LP-00)  




implement a dphy_frm: which inculd the pattern gen part and receive check part  
1 lane relative to a dphy_frm, if using 4 lanes xilinx dphy module, it will need 4 dphy_frm  
dphy_frm_gen:  
dphy_frm_chk:  
