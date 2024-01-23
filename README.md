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

mode: 
1. high speed data mode
2. esc mode
3. ulps mode


implement a dphy_frm: which inculd the pattern gen part and receive check part  

dphy_frm_gen:  
dphy_frm_chk:  
