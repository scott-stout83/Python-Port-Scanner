# Python-Port-Scanner
Basic port scanner in python

#!/usr/bin/python

import socket

def port_scanner(host, start_port, end_port): <br/>
 &nbsp;&nbsp;&nbsp;&nbsp;         for port in range(start_port, end_port+1): <br/>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;              sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM) <br/>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;              sock.settimeout(1) <br/>
   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;               result = sock.connect_ex((host, port)) <br/>
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;             if result == 0: <br/>
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                     print(f"Port {port} is open") <br/>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                    sock.close() <br/><br/><br/>


host = input("Enter Target IP: ") <br/>
start_port = int(input("Enter Start Port: ")) <br/>
end_port = int(input("Enter End Port: ")) <br/><br/>

port_scanner(host, start_port, end_port)
