### 16X2 Display + IC2 + Pi
- [Youtube demo to display on screen](https://www.youtube.com/watch?v=3XLjVChVgec)
- [Arduino + 16X2 + IC2](https://www.youtube.com/watch?v=f6Gz4I4-UjU)


### Screen display

```
#include <Wire.h> 
#include <LiquidCrystal_I2C.h>

LiquidCrystal_I2C lcd(0x27, 16, 2);

void setup()
{

	lcd.begin();


	lcd.backlight();
	lcd.clear();
	lcd.setCursor(4,0);
	lcd.print("Hackster");
}

void loop()
{
}
```
