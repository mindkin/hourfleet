## Verifying Car Kit Before Installation  

It's a good idea to verify that the car kit has internet connectivity BEFORE installing it in your car. We have designed the car kit so that it can be powered on your desk using a regular 12v mains (100-230v) adapter, and this allows you to confirm that the [cellular modem connects to the internet using your SIM](http://docs.hourfleet.com/carkit.html#cellular-connectivity). Follow these steps.
1. Insert your standard sized SIM into the cellular modem as shown below

![SIM](http://docs.hourfleet.com/images/carkit/ModemSIM.png)  

2. Connect the modem to the 10cm black cable which is already attached to the main unit
2. Connect the Tap sensor
2. Connect the 'barrel' power supply to your mains power. The result will be
   - The main unit will show a steady red LED, and a steady green LED
   - The Tap sensor will show a flashing red LED
   
At this point the car kit is booting up and will will shortly request a set of encrypted QR keys from the Hourfleet server. When these keys arrive the Tap unit LED will begin flashing purple, and once all QR keys have been received the Tap unit will begin a slow blue flash sequence.

Once you see the Tap unit flashing slow blue, wait 15 minutes for the device to 'sleep'. You can tell the car kit is asleep when
1. The White/Red modem LED is off
1. The only LED showing on the car kit is an infrequent, short flasg of the red LED

With the unit asleep you can disconnect the 12v power supply. 

Important: We ship your device with the Hourfleet server configured to send dummy QR keys to your car kit. With the steps above confirming these dummy keys are being deliver, the next step to for you to contact us and ask to enable live QR keys.

## Registering the Carkit on Your Car Share

At this point you will have confirmed the following:
1. That your SIM card and cellular operator account provides cellular data access for the car kit
1. That Hourfleet has sucessfully delivered dummy QR keys to the Tap sensor
1. That the Hourfleet server is ready to send live QR keys to the Tap sensor

The next step is to register your car kit. This creates an association between one specific car kit, and the matching car which you have  already  set up in Hourfleet.  Let's gather the information you need.
- Make a note of  the **license plate** of the car
- Make a note of the number on the **sticky label under the main carkit unit**. Ignore the sticky label on the key unit. This number will be 8 digits long.

You will need both of these to complete the electronic registration in the Hourfleet App next.

Open the Hourfleet App at your Car Share URL ( `https://yourcompany.hourfleet.com`), login and go to the 'Operations' dashboard.

- From the menu of the far left, click  'Cars', and then 'Carkits'
- Enter the license plate number of the car, and hit 'Search'
- When the car is found, enter the Device Id, which is the 8 digit number you noted from the sticky label on the main carkit unit. 
- Click 'Register' 

![CarKit Registration](images/Operations_CarkitRegistration.png)

## Installing the Carkit  

The Hourfleet carkit is simple to install, and some customers may choose to do this themselves. Even so, we strongly recommend that this  work is undertaken by a professional. They will be able to advise you on the best practice for your car, and ensure the installation is safe, secure and asthetically pleasing. Installation should take less than 15 minutes per car.

Familiarize yourself with the following parts:

1. The carkit Main Unit and the Car Key Unit
2. The GPS Antenna
3. The Touch Sensor
4. The OBD Connector  
5. The red/white cellular modem (not shown)  

![CarKit](images/carkit/OpticalCarkit_AccessoriesLabeled.jpg)

The recommended installation process is as follows. 

1. Identify where you wish to locate the main unit. We recommend installing the car kit under the dashboard (or above the footwell) on the drivers side of the car. All cars are different in how they are configured here, so you'll need to consider the physical space and proximity to the three primary peripherals.

2. Leave the adhesive pads covers and locate the Touch Sensor one the windscreen as low and as close the drivers side of the windscreen, so it does not obstruct the drivers view of the road. Ideally, place it at the same height as an average persons elbow. This makes it very accessible to operate for Tap Tap Go outside the car for most people. Run the cable down behind the dashboard to into the area that you'll be afixing the main device. This is the bit that is most likely to require professional support.
**Important**: Take care locating and confirming the placement. Once you remove the adhesive covers and place the Tap Tap Go device on the windscreen is very difficult to remove.

2. The GPS antenna should be placed on the dashboard towards the windscreen. The cabl is sufficiently long to allow it to be placed in either side of the car. What is important is that the antenna unit has a 'clear view' of the sky. For this reason we recommend keeping it 5+ centimeters in from the A pillar. The antenna is supplied with an adhesive mounted metal disk. The antenna inself is magnetic, and it is placed on the metal disk once it is adhered to the dashboard. Run the cable down behind the dashboard to into the area that you'll be afixing the main device. This is the bit that is most likely to require professional support.  

3. Locate the OBD connector. This is usually near the steering column, and it may be accessed from underneath the footwell, or from a removable panel. This is the source of car telematics data, and also of power for the car kit. Connect the OBD 'flat noodle' cable to the OBD connector and run it into the area that you'll be afixing the main device.  

4. At this point you should have three cables available in the area that you'll be afixing the main device. Connect the Tap Tap Go to the main device. It should be a snug fit through the case, but force should not be used lets you accidentlly damage the main device.  

5. Connect the GPS antenna to the main device. Twist until finger tight. You should tighten very gently with a small spanner.  

6. The last thing to connect is the ODB cable. When you do this the device will power up initially showing red and greed LEDs. Once powered up, as indicated by red and green LEDs, we recommend that you do not remove the OBD cable for any reason. If you do wish to remove the device waiting 20 minutes should have the main device showing no green LED, and a slow flashing red LED. When the device is in this state it is ok to disconnect it from its OBD power source.  

7. With the device connect and powered it's time to secure it in the position that you selected earlier. The following are important considerations:  
- The device should be secured firmly in place  
- The cellular modem should also be secured. This can be achieved by using professional tape to afix it to the main device  
- Any spare cable should be secured away from the footwell
**Important**: It is critical that the safe operation of the car by drivers is in no way impeded by the placement of the main device, of by any of the cables. Your chosen installer will be able to advise you on the best practice for your car, and ensure the installation is safe, secure and asthetically pleasing.  



### OBD Connector

Plug the ODB Connector into the Onboard Diagnostics (OBD) connector of the car, which should also under the dashboard. 

This connector can be located in different places in different cars, usually at least one connection under the dashboard.

![OBD Connector](images/carkit/OBD2Port.png)

### GPS Antenna

Then, you route the GPS Antenna cable from the Main Unit up onto sit on the dashboard. It can be on either the drivers side of the car or the passengers side. Ideally, you would route the GPS Antenna cable out of sight behind the dash. Place the GPS Antenna in plain sight of the windscreen, either on the dashboard, or adhered to the windscreen near the top of the windscreen, with a clear view of the sky, and not obscured by any stickers on the windscreen.

### Touch Sensor  

Then you route the Touch Sensor cable from the main unit up onto the dashboard and up the side of the windscreen. Like the GPS cable, try to route the Touch Sensor cable out of sight behind the dash. Run the Touch Sensor cable up along the vertical support column that supports the side of the windscreen on either the drivers or passengers side. This is the vertical column between the glass of the windscreen and the glass of the side door window. Adhere the Touch Sensor to the windscreen as low and as close the drivers side of the windscreen, so it does not obstruct the drivers view of the road. Ideally, place it at the same height as an average persons elbow. This makes it very accessible to operate for Tap Tap Go outside the car for most people.



## Verify the Physical Installation

Now that the carkit has been physically installed and electronically registered. Check that the OBD connector has been connected successfully, you should see a slow flashing red light on the Touch Sensor in the window screen (from the outside of the car). This confirms that the device is working correctly.

> If the red light is not flashing, then check your OBD connector

For the next part, you will need the other spare (proximity) car key for the car.

You will need to start the car, as you do normally with the start button.

For the next part, the car has to be in a location where it has cellular access to the internet.

You may need to move the car to do this, or drive around for a few minutes in a cell covered area.

Either way, after a few minutes, you will notice that the red flashing light on the Touch Sensor will change from flashing red to flashing blue. It may, flash purple for a few seconds turning from red to blue. This may take anywhere between 2 and 15 mins.

Once the Touch Sensor turns to flashing blue. You may stop the car. 

The carkit is now fully programmed and can now be used by your customers (through the Hourfleet app) key-lessly without any physical keys. All they need is a smartphone with internet access!

### Troubleshooting Physical Installation

From the moment the carkit is first powered to the moment it is fully configured and ready for lock/unlock operation, will be about 2-15 mins. 

The LED light in the windscreen indicates the car kit's current state:  

- **No light**: Tap, Tap is disabled. Either the device is not correctly powered, or the car has detected vibrations over the last 5 secs, such as vibrations from driving down the road.
- **Red flashing (slow)**: Power is applied. The car kit is not yet configured, and is waiting to connect to Hourfleet over the internet, for which it needs cellular coverage.
- **Purple flashing** : The car kit is configured by the Hourfleet.
- **Green pulsing**: Ready for presentation of a unlock/lock key, in response to a Tap, Tap on the window screen.
- **Blue flashing** : Ready for normal lock/unlock operation.
- **Green flashing**: A valid QR key has been presented. The car doors will unlock or lock as appropriate.


