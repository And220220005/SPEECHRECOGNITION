# SPEECHRECOGNITION
Speech Recognition System using Arduino
#include <Adafruit_LiquidCrystal.h>

int flex_sensor = 0;

Adafruit_LiquidCrystal lcd_1(0);

void setup()
{
  pinMode(A0, INPUT);
  Serial.begin(9600);
  lcd_1.begin(16, 2);
}

void loop()
{
  flex_sensor = analogRead(A0);
  Serial.println(flex_sensor);
  lcd_1.setCursor(0, 0);
  lcd_1.print("SIGH LANGUAGE");
  if (flex_sensor < 150) {
    lcd_1.setCursor(0, 1);
    lcd_1.print("Drink Water");
  } else {
    lcd_1.setCursor(0, 1);
    lcd_1.print("Nothing                          ");
  }
  delay(10); // Delay a little bit to improve simulation performance
}
