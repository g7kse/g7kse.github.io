---

title: Maidenhead
date: 2024-09-28
description: A try at manipulating maidenhead locators using python
author: Alex
type: docs
prev: docs/hamtool
next: docs/msftime
tags:
  - python
  - ham radio
  - coding
---

This little snippet of code is handy for showing maidenhead locator from a GPS input. It uses the [TinyGPS++]{http://arduiniana.org/libraries/tinygpsplus/} library to do the heavy lifting with just a small spot of maths to calculate the maidenhead locator. Just watch out for LCD pin connections and the GPS baud and pinout value. I have no idea where the code came from, I'm 99% sure that I pinched most of it from somewhere else but can't attribute it because I did this 10 years ago.

```
#include <TinyGPS++.h>
#include <SoftwareSerial.h>
#include <LiquidCrystal.h>
/*
   This sample sketch demonstrates the normal use of a TinyGPS++ (TinyGPSPlus) object.
   It requires the use of SoftwareSerial, and assumes that you have a
   4800-baud serial GPS device hooked up on pins 4(rx) and 3(tx).
*/
static const int RXPin = 8, TXPin = 9;
static const uint32_t GPSBaud = 9600;

// The TinyGPS++ object
TinyGPSPlus gps;

// The serial connection to the GPS device
SoftwareSerial ss(RXPin, TXPin);

//Set up LCD
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

void setup()
{
  
  ss.begin(GPSBaud);
  lcd.begin(16, 2);

    lcd.print("GPS-IARU Locator");
      delay(3000);
      
    lcd.setCursor(4, 1);
    lcd.print("by G7KSE");
 
      delay(2500);
      
      lcd.clear();
}

void loop()
{
  // This sketch displays information every time a new sentence is correctly encoded.
  while (ss.available() > 0)
    if (gps.encode(ss.read()))
      displayInfo();

  if (millis() > 5000 && gps.charsProcessed() < 10)
  {
    lcd.println(F("No GPS detected: check wiring."));
    while(true);
  }
}

void displayInfo()
{
  long lat, lon;
   if (gps.location.isValid());
{ 
     lon = 10000000 * gps.location.lng() + 1800000000;
     lat = 10000000 * gps.location.lat() + 900000000;
}

char MH[10] = {'A', 'A', '0', '0', 'a', 'a'}; // Initialise our print string
  MH[0] +=  lon / 200000000; // Field
  MH[1] +=  lat / 100000000;
  MH[2] += (lon % 200000000) / 20000000; // Square
  MH[3] += (lat % 100000000) / 10000000;
  MH[4] += (lon % 20000000) / 833333; // Subsquare .08333 is 5/60
  MH[5] += (lat % 10000000) / 416666; // .04166 is 2.5/6 
  MH[6] += (lon % 2000000) / 125000; // Subsquare .08333 is 5/60
  MH[7] += (lat % 1000000) / 100000; // .04166 is 2.5/6 
  //MH[8] += (lon % 200000) / 8333; // Subsquare .08333 is 5/60
  //MH[9] += (lat % 100000) / 4166.66; // .04166 is 2.5/6
  
  
   String MH_txt = ""; // Build up Maidenhead
  int i = 0; // into a string that's easy to print
  while (i < 6)
  {
    MH_txt += MH[i];
    i++; 
  }
   {
    lcd.setCursor(0, 0);
    lcd.print("Current  Locator");
    
    lcd.setCursor(5, 1 );
    lcd.print(MH);
     
   }
}

```