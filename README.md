# PS2 MOUSE INTERFACE WITH MICROCONTROLLER 
This tutorial describes the way of interfacing a PS2 mouse with a microcontroller
(atmega 16/32) and getting the mouse output on LCD.
## CONNECTIONS


PS2 mouse can be connected to atmega using two type of connectors:
- 1.5-pin DIN connector

- 2.6 pin mini connector

Connector pin arrangement


## PS2 ALGORTHIM
The PS2 port uses an in-out clock to transmit and receive data.Data is send and
received and send synchronous to this clock.Mouse generates the clock signal and
data is read at the falling edge of the clock.
Data is: 1 start bit,8 data bits, 1 parity bit, 1 stop bit



For the host to send a command to mouse, it first brings the clock low for at least
100 microseconds.then it brings data line low.then clock line ir released.data line is
reset before sending the command after which the data line is released.Then the
device wait for data line and clock line to be low. After every successful command
an acknowledgement is received by the host from the mouse. 

## DATA BYTES
On mouse moves the mouse sends 3 bytes of information through the ps-2 port.

The contents of the data packet is described below in the diagram: 


Byte 1 contains information on the direction the mouse moved wrt its previous

position, status of the mouse buttons (0 for not pressed and 1 for pressed) and the x

and y overflows which are set if the counters go past 255. Byte 2 and 3 contain

information regarding the x movement and the y movement.

For detailed information refer:http://www.computer-engineering.org/

## C CODE FOR MOUSE INTERFACING
#### MOUSE IS WORKING IN REMOTE MODE.
##### IN THE GIVEN CODE 
- __Pxy(data line pin ) is PINB.1__

- __Pxy(clock line pin) is PINB.0__

A __LCD__ is also interfaced to get the state of mouse(_click and position_)on it.

The __link__ for the c code of ps2mouse is given below

https://docs.google.com/document/d/1gYyS4Z4tWFrQ01jmDc9xl8kwchjnAfCA4aQYuJhpgN8/edit?hl=en_US
