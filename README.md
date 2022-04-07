# firmware


import serial

ser = serial.Serial(port='/dev/tty50', 
                    baudrate=9600, parity=serial.PARITY_NONE, 
                    stopbits=serial.STOPBITS_ONE, 
                    bytesize=serial.EIGHTBITS, 
                    timeout=1)

while 1:
    x=ser.readline()
    if len(x) > 0:
        print("RFID code is :", x.hex())
