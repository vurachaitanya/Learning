## Using Pi3 LED Blinking 

https://raspberrypihq.com/making-a-led-blink-using-the-raspberry-pi-and-python/

## Reference of PI Pins :

https://www.jameco.com/Jameco/workshop/circuitnotes/raspberry-pi-circuit-note.html


```
# apt-get install python-rpi.gpio python3-rpi.gpio

# cat led.py

import RPi.GPIO as GPIO # Import Raspberry Pi GPIO library
from time import sleep # Import the sleep function from the time module
GPIO.setwarnings(False) # Ignore warning for now
GPIO.setmode(GPIO.BOARD) # Use physical pin numbering
GPIO.setup(8, GPIO.OUT, initial=GPIO.LOW) # Set pin 8 to be an output pin and set initial value to low (off)
while True: # Run forever
 GPIO.output(8, GPIO.HIGH) # Turn on
 sleep(1) # Sleep for 1 second
 GPIO.output(8, GPIO.LOW) # Turn off
 sleep(1) # Sleep for 1 second
 ```
 ## Funny blinking 
 ```
 import RPi.GPIO as IO
import time
IO.setwarnings(False)
IO.setmode(IO.BCM)

IO.setup(2,IO.OUT) #GPIO 2 -> Red LED as output
IO.setup(3,IO.OUT) #GPIO 3 -> Green LED as output
IO.setup(14,IO.IN) #GPIO 14 -> IR sensor as input

while 1:

    if(IO.input(14)==True): #object is far away
        IO.output(2,True) #Red led ON
        time.sleep(1)
        IO.output(2,False) # Red led OFF
        IO.output(3,True) # Green led OFF
        time.sleep(1)
        IO.output(3,False) #Green led ON

    if(IO.input(14)==False): #object is near
        IO.output(3,True) #Green led ON
        time.sleep(5)
        IO.output(3,False) #Green led ON
        IO.output(2,True) # Red led OFF
        time.sleep(4)
        IO.output(2,False) # Red led OFF

 ```
