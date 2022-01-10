### 16X2 Display + IC2 + Pi
- [Youtube demo to display on screen](https://www.youtube.com/watch?v=3XLjVChVgec)
- [Arduino + 16X2 + IC2](https://www.youtube.com/watch?v=f6Gz4I4-UjU)
- [I2c Library's](https://github.com/fdebrabander/Arduino-LiquidCrystal-I2C-library)

### Screen display

```
#include <Arduino.h>
#include <Wire.h> 
#include <LiquidCrystal_I2C.h>

// Set the LCD address to 0x27 for a 16 chars and 2 line display
LiquidCrystal_I2C lcd(0x27, 16, 2);

void setup()
{
	// initialize the LCD
	lcd.begin();

	// Turn on the blacklight and print a message.
	lcd.backlight();
	lcd.print("Darpad & Srinidhi");
}
void loop()
{
	// Do nothing here...
}
```
- Display 2 lines
```
#include <LiquidCrystal_I2C.h>
#include <Arduino.h>
#include <Wire.h> 
//LiquidCrystal_I2C(0x27, 16, 2);
LiquidCrystal_I2C lcd(0x3F,16,2);  // set the LCD address to 0x3F for a 16 chars and 2 line display

void setup() {
  //lcd.init();
  lcd.begin();
  lcd.clear();         
  lcd.backlight();      // Make sure backlight is on
  // Print a message on both lines of the LCD.
  lcd.setCursor(2,0);   //Set cursor to character 2 on line 0
  lcd.print("Hello Darpad !");
  lcd.setCursor(2,1);   //Move cursor to character 2 on line 1
  lcd.print("Hello Nidhi !");
}

void loop() {
}
```

- Scrolling
```
#include <Wire.h>
#include <Arduino.h>
#include <LiquidCrystal_I2C.h>
//LiquidCrystal_I2C lcd(0x27, 2, 1, 0, 4, 5, 6, 7, 3, POSITIVE);
//LiquidCrystal_I2C lcd(0x27, 2);
LiquidCrystal_I2C lcd(0x27, 16, 2);
void setup()
{
lcd.begin(16, 2); 
  // Print a message to the LCD.
  lcd.backlight();
  lcd.setCursor(0,0);
  lcd.print(" WELCOME TO STEEMIT ");   
}
void loop()
{
   lcd.setCursor(16,1);
   lcd.autoscroll();    // Set diplay to scroll automatically
   lcd.print(" ");      // set characters
   delay(700);    
}
```

