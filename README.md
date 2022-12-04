### Wokwi
https://wokwi.com/projects/347144898258928211

## UART String Transmitter

Supports sending multiple ASCII characters over UART.

Each column of flip flops stores a single ASCII character. To modify a character, change bits 6-0 by modifying whether the respective multiplex is set to VCC or GND. 

To add characters, copy and paste a column. Connect the output of the new column (Q port of the upper-most D-flip flop) to the input of the stage to the left (bottom-left most multiplexer port). Remember to connect the multiplexer select signal and the clock to the new column as well.

Lastly, delete the the output of the first column (Q port of the upper-most D-flip flop) and create a new connection to the to the input of the new stage you've added (bottom-left most multiplexer port).

**How to use**

To begin transmission:
1. Set the Arduino serial baud rate `Serial.begin(<baud rate>);` in the *.ino file to 300
2. Set the Wokwi clock frequency `"attrs": { "frequency": "300" }` in the diagram.json to 300 as well 
3. Set the slide switch to the clock
4. Set SW7 to OFF ("Load")
5. Set SW8 to ON ("Output Enable")
6. Set SW7 to ON ("TX")

If there's no output from the Wokwi Arduino serial monitor, try toggling SW7 OFF and ON again.

Congratulations! You should now see your customized letters being output!

Note that garbage characters may be printed upon initialization.
| SW      | Function| 
|---------|---------|
| 1       | N/A     | 
| 2       | N/A     |
| 3       | N/A     |
| 4       | N/A     | 
| 5       | N/A     | 
| 6       | N/A     |
| 7       | Load/TX | 
| 8       | Out. En.| 
