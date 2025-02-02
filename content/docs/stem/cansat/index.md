---
title: CanSat
date: 2024-01-01
description: A satellite the size of a soft drinks can
author: Alex
type: docs
next: /lego_league
tags:
  - RPi
  - LoRa
  - STEM
---

This is a bit of library documentation. CANSAT is a project from ESA for 6th Form and Undergraduate students to build a 'satellite' that will be launched using a model rocket. the project has a primary and secondary mission. the primary being stipulated and the secondary being a choice.

The couple of years I was involved with the project, the primary mission was to measure the temperature and humidity of the atmosphere within the satellite. pretty straightforward stuff. the bit that the studenst struggeld a bit with was programming the RPi Pico, making up SMA cables and dealing with the data once it came back to the ground station.

So here's a bit of stuff that I collected. The basic breadboard details are below with super basic RX, TX and TX code with GPS for the primary mission. Using teh Picos and circuit python

![TX Board](txboard.jpg#cente)

![RX Board](rxboard.jpg#cente)


### Receiver code
```
  import digitalio
  import board
  import time
  import adafruit_rfm9x
  import busio
  import math

  '''
  Define the pins for the RFM9x receiver
  CLK = GP2
  MOSI = GP3
  MISO = GP4
  CS = GP6
  Reset = GP7
  '''
  spi = busio.SPI(clock=board.GP2, MOSI=board.GP3, MISO=board.GP4)
  cs = digitalio.DigitalInOut(board.GP6)
  reset = digitalio.DigitalInOut(board.GP7)
  rfm9x = adafruit_rfm9x.RFM9x(spi, cs, reset, 433.0) # set the receive frequency to 433MHz

  def try_read():
      return rfm9x.receive(timeout=1.0)

  def rssi():
      return rfm9x.rssi
  '''
  Blink the light as a watchdog to show that the programme is running
  '''

  led = digitalio.DigitalInOut(board.LED)
  led.direction = digitalio.Direction.OUTPUT

  print("Waiting for packets...")

  while True:
      led.value = not led.value
      packet = rfm9x.receive()
      quality = (rssi()+ 100)*2 # a crude way of having a relative and positive value for the Serial Studio dashboard
      packet_count = 0
      if packet is not None:
          packet_text = str(packet, 'ascii')
          print ("/*" + '{0}'.format(packet_text),('{0}'.format(quality)) + "*/") # format the data as a frame that can be read in Serial Studio
          packet_count = packet_count + 1
```

### TX code
```
  import board
  import digitalio
  import time
  import busio
  import adafruit_bmp280
  import adafruit_rfm9x

  #define the LED
  led = digitalio.DigitalInOut(board.LED)
  led.direction = digitalio.Direction.OUTPUT

  '''
  Set up the BMP280. Pins used are:
  SCL = GP15
  SDA = GP14
  Then define the temperature, pressure and altitude
  '''

  i2c = busio.I2C(scl=board.GP15, sda=board.GP14)
  bmp280 = adafruit_bmp280.Adafruit_BMP280_I2C(i2c, address=0x76)

  def sat_temp():
      return bmp280_sensor.temperature

  def sat_pressure():
      return bmp280_sensor.pressure
    
  def sat_alt():
      return bmp280_sensor.altitude

  '''
  Set the local atmospheric pressure (QNH). This will be used to calculate the altitude. 
  Note that sea level pressure can be your local pressure so a local weather report for that day will suffice.
  Its important to note that the sensor only infers altitude for the pressure so it will have
  inaccuracies.
  '''
  bmp280.sea_level_pressure = 1034

  '''
  Define the pins for the RFM9x transmitter
  CLK = GP2
  MOSI = GP3
  MISO = GP4
  CS = GP6
  Reset = GP7
  Then define the parameters for sending the message payload
  '''
    
  spi = busio.SPI(clock=board.GP2, MOSI=board.GP3, MISO=board.GP4)
  cs = digitalio.DigitalInOut(board.GP6)
  reset = digitalio.DigitalInOut(board.GP7)
  rfm9x = adafruit_rfm9x.RFM9x(spi, cs, reset, 433.0) # set the transmit frequency to 433MHz

  def send(message):
      rfm9x.send(message)

  while True:

      led.value = not led.value
      Id = "CanSat Example,"
      sat_time = str("%.0f," % (time.monotonic()))# + " s"
      temp = str("%.1f," % (bmp280.temperature))# + " C"
      pressure = str("%.0f," % (bmp280.pressure))# + " hPa"
      altitude = str("%.1f," % (bmp280.altitude))# + " meters"
      Payload = Id + sat_time + temp + pressure + altitude # message payload string
      rfm9x.send(Payload)
      print(Payload)
      time.sleep(1)
```

### TX Code with GPS
```
  import board
  import digitalio
  import time
  import busio
  import adafruit_bmp280
  import adafruit_rfm9x
  import adafruit_gps

  #Setup GPS
  uart = busio.UART(board.GP16, board.GP17, baudrate=9600, timeout=10)# set up uart
  gps = adafruit_gps.GPS(uart, debug=False)#create gps module instance
  gps.send_command(b"PMTK314,0,1,0,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0")#Turn on the basic GGA and RMC info (what you typically want)
  gps.send_command(b"PMTK220,1000")#set update rate (1second)
  last_print = time.monotonic()


  #define the LED
  led = digitalio.DigitalInOut(board.LED)
  led.direction = digitalio.Direction.OUTPUT

  '''
  Set up the BMP280. Pins used are:
  SCL = GP15
  SDA = GP14
  Then define the temperature, pressure and altitude
  '''

  i2c = busio.I2C(scl=board.GP15, sda=board.GP14)
  bmp280 = adafruit_bmp280.Adafruit_BMP280_I2C(i2c, address=0x76)

  def sat_temp():
      return bmp280_sensor.temperature

  def sat_pressure():
      return bmp280_sensor.pressure
    
  def sat_alt():
      return bmp280_sensor.altitude

  '''
  Set the local atmospheric pressure (QNH). This will be used to calculate the altitude. 
  Note that sea level pressure can be your local pressure so a local weather report for that day will suffice.
  Its important to note that the sensor only infers altitude for the pressure so it will have
  inaccuracies.
  '''
  bmp280.sea_level_pressure = 1034

  '''
  Define the pins for the RFM9x transmitter
  CLK = GP2
  MOSI = GP3
  MISO = GP4
  CS = GP6
  Reset = GP7
  Then define the parameters for sending the message payload
  '''
  '''
  spi = busio.SPI(clock=board.GP2, MOSI=board.GP5, MISO=board.GP4)
  cs = digitalio.DigitalInOut(board.GP6)
  reset = digitalio.DigitalInOut(board.GP7)
  rfm9x = adafruit_rfm9x.RFM9x(spi, cs, reset, 433.0) # set the transmit frequency to 433MHz

  def send(message):
      rfm9x.send(message)
  '''
  while True:
      
      gps.update()
      # Every second print out current location details if there's a fix.
      current = time.monotonic()
      if current - last_print >= 1.0:
          last_print = current
          if not gps.has_fix:
              # Try again if we don't have a fix yet.
              print("Waiting for fix...")
              continue
          # We have a fix! (gps.has_fix is true)
          
          sat_time = "{:02}:{:02}:{:02},".format(
                      gps.timestamp_utc.tm_hour,  
                      gps.timestamp_utc.tm_min,
                      gps.timestamp_utc.tm_sec,
                      )
          
          sat_date = "{}/{}/{},".format(
                      gps.timestamp_utc.tm_mday,
                      gps.timestamp_utc.tm_mon,
                      gps.timestamp_utc.tm_year,
                      )

          print("=" * 70)  # Print a separator line.
          
          #Define the payload strings
          Id = "CanSat Example,"
          temp = str("%.1f," % (bmp280.temperature))# + " C"
          pressure = str("%.0f," % (bmp280.pressure))# + " hPa"
          lat = str("%.4f," % (gps.latitude))
          long = str("%.4f," % (gps.longitude))
          gps_alt = str("%.1f," % (gps.altitude_m))
          sats = str("%.0f" % (gps.satellites))
          json_start = str("/*")
          json_end = str("*/")
      
          Payload = json_start + Id + sat_time + sat_date + temp + pressure + lat + long + gps_alt + sats + json_end # message payload string with json markers
          
          #Send the message payload
          rfm9x.send(Payload)
          print(Payload)# print it in the serial terminal for good measure
          
          led.value = not led.value #Flash the led after the payload is sent
          print("=" * 70)
```

### Collecting the data

By far and away the nicest way to handle the data was in json format. This meant it was easily handled by external applications and so dashboards can be made up which look pretty impressive. The students used [Serial Studio](https://serial-studio.github.io/) which worked a treat. A bit hard for some to get their heads round but it runs on a RPi or a laptop, gives great visuals and shows how data can be handled. I'm sure it can be done with other tools but this was the one we used. Probably be easy to do in PowerBI or Tableau but that wasn't the plan

![Serial Studio](serial.png#cente)

### Dev boards

Lastly I made up some development boards to help do stuff in class. They're still kicking about in KiCAD but are probably long out of date for pinouts etc. They were a great way to get the students to stop breaking stuff, here for legacy reasons. If you want one the I can supply the KiCAD files. But they probably need a good looking at.