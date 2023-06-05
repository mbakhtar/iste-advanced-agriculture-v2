# Automatic Irrigation System
```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
ledRing=github:climate-action-kits/pxt-fwd-edu
soilMoisture=github:climate-action-kits/pxt-fwd-edu
```
## Step 1 @showdialog
Plug your USB cable into the micro:bit and insert it into the Climate Action Kit board. Click on the button to the right of download and follow the steps to pair your micro:bit.![Plug your USB cable into the micro:bit and insert it into the Climate Action Kit board. Click on the button to the right of download and follow the steps to pair your micro:bit.](https://raw.githubusercontent.com/mbakhtar/iste-advanced-agriculture-v2/master/pair%20microbit-280x203.gif)

## Step 2
Click on the ``||fwdSensors:Sensors||`` drawer and 
find the ``||fwdSensors:set all ledRing LEDs to 10||``block.
Drag the block under the forever loop and download the code to your micro:bit to activate your LED.
Click on the bulb to show your hint.
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(10)
    )}
```
## Step 3
Open the ``||logic: Logic||`` drawer and add a ``||logic:If Else||`` statement to your code.
Click the ``||fwdSensors:Sensors||`` drawer and add ``||fwdSensors:is soilMoisture1 moisture level over 5%||`` 
to the ``||logic:true||`` condition of the ``||logic:If Else||`` block.
Click on the bulb to show your hint.
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(10)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(5, fwdSensors.thresholdDirection.over)) {
          } 
    else {
        }
        )}
```
## Step 4
To show when your plant needs watering or not, go to the ``||basic:basic||`` 
drawer and drag the 
``||basic:show icon||`` block. Nest it under the ``||logic:if||`` condition. 
Change the icons to a smiley ``||basic: :)||`` and ``||basic: :(||``.
Click on the bulb to show your hint.
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(10)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(5, fwdSensors.thresholdDirection.over)) {
          basic.showIcon(IconNames.Happy)} 
    else {
        basic.showIcon(IconNames.Sad)}
        )}
```
## Step 5
Check your code by downloading it and holding the moisture sensor between 
your fingers. When you hold this sensor, the simulator will indicate the moisture level and display a ``||basic::)||``
and when you let go, it should display ``||basic: :(||``.

## Step 6
To automatically water your plant when the soil is dry, go to the
``||fwdMotors:Motors||`` drawer  and add ``||fwdMotors:run pump for 500||`` under the 
 ``||basic: :(||`` in the ``||logic:If Else||`` block.
Click on the bulb to show your hint.
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(8323327)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(50, fwdSensors.thresholdDirection.over)) {
        basic.showIcon(IconNames.Happy)
        } else {
        basic.showIcon(IconNames.Sad)
        fwdMotors.pump.fwdTimedRun(500)
        }
})
```
## Step 7
To let the water soak in before your moisture sensor can detect water again, 
go to your ``||basic:basic||`` drawer 
to add a ``||basic:pause (ms) 500||`` 
and a ``||basic:clear screen||`` block after your
``||fwdMotors:run pump for 500||`` block.
Click on the bulb to show your hint.   
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(8323327)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(50, fwdSensors.thresholdDirection.over)) {
        basic.showIcon(IconNames.Happy)
        } else {
        basic.showIcon(IconNames.Sad)
        fwdMotors.pump.fwdTimedRun(500)
        basic.pause(500)
        basic.clearScreen
        }
})
```
## Step 8
Attach your moisture sensor to your project and place the tube in one empty cup. 
Then download your code to test your automated watering system.
Click on the bulb to show your hint.

## Step 9
Congratulations on completing your Automatic Irrigation System! 
Go back to the Forward Edu lesson for more activities and extensions
