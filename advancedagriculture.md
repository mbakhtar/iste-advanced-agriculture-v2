# Automatic Irrigation System
```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
ledRing=github:climate-action-kits/pxt-fwd-edu
soilMoisture=github:climate-action-kits/pxt-fwd-edu
```
## Step 1 @showdialog
Plug your USB cable into the micro:bit and insert it into the 
Climate Action Kit board. 
![breakout board](https://raw.githubusercontent.com/mbakhtar/wind-turbine-lesson-tutorial/master/breakout-resized.png)

## Step 2 @showhint
Click on the button to the right of download and follow the steps to pair your micro:bit.
![pair gif](https://raw.githubusercontent.com/mbakhtar/iste-electric-vehicle-v1/master/pair%20microbit-280x203.gif)

## Step 3
Click on the ``||fwdSensors:Sensors||`` drawer and 
find the ``||fwdSensors:set all ledRing LEDs to 10||``block.
Drag and drop the block under the ``||basic:forever||`` loop.
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(10)
    )}
```
## Step 4
Click on the ``||logic: Logic||`` drawer and add a ``||logic:If then Else||``
block inside/under the ``||basic:forever||`` loop.
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(10)
    if (true) {
          } 
    else {
        }
        )}
```
## Step 5
Click the ``||fwdSensors:Sensors||`` drawer and add ``||fwdSensors:is soilMoisture1 moisture level over 5%||`` 
to the ``||logic:true||`` condition of the ``||logic:If then Else||`` block.
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(10)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(5, fwdSensors.thresholdDirection.over)) {
          } 
    else {
        }
        )}
```
## Step 6
To show when your plant needs watering or not, go to the ``||basic:basic||`` 
drawer and drag the ``||basic:show icon||`` block. 
Place it or Nest it under the ``||logic:if then||`` condition. 
Change the icon to a ``||basic: :)||`` smiley.
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(10)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(5, fwdSensors.thresholdDirection.over)) {
          basic.showIcon(IconNames.Happy)} 
    else {
        }
        )}
```
## Step 7
To add a sad ``||basic::(||`` smiley go to the ``||basic:basic||`` 
drawer and drag the ``||basic:show icon||`` block. 
Place it or Nest it under the ``||logic:Else||`` condition. 
Change the icon to a ``||basic: :(||`` smiley.
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(10)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(5, fwdSensors.thresholdDirection.over)) {
          basic.showIcon(IconNames.Happy)} 
    else {
        basic.showIcon(IconNames.Sad)}
        )}
```
## Step 9
To automatically water your plant when the soil is dry, go to the
``||fwdMotors:Motors||`` drawer  and add ``||fwdMotors:run pump for 500||`` under the 
 ``||basic: :(||`` smiley in the ``||logic:Else||`` block.
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(8323327)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(50, fwdSensors.thresholdDirection.over)) {
        basic.showIcon(IconNames.Happy)
        } else {
        basic.showIcon(IconNames.Sad)
        fwdMotors.pump.fwdTimedRun(100)
        }
})
```
## Step 10
To let the water soak in before your moisture sensor can detect water again, 
go to your ``||basic:basic||`` drawer, add a ``||basic:pause (ms) 100||`` block,
after your ``||fwdMotors:run pump for 500||`` block. 
Change the ``||basic:100||`` to ``||basic:500||``
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(8323327)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(50, fwdSensors.thresholdDirection.over)) {
        basic.showIcon(IconNames.Happy)
        } else {
        basic.showIcon(IconNames.Sad)
        fwdMotors.pump.fwdTimedRun(500)
        basic.pause(500)
        basic.clearScreen()
        }
})
```
## Step 11
Click on the ``||basic:basic||`` drawer and find ``||basic:clear screen||`` 
block. Add ``||basic:clear screen||`` block after the ``||basic:pause (ms) 500||``
block.
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(8323327)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(50, fwdSensors.thresholdDirection.over)) {
        basic.showIcon(IconNames.Happy)
        } else {
        basic.showIcon(IconNames.Sad)
        fwdMotors.pump.fwdTimedRun(500)
        basic.pause(500)
        basic.clearScreen()
        }
})
```
## Step 12
Attach your moisture sensor to your project and place the tube in one empty cup. 

## Step 13
A dry run test is to hold the moisture sensor between your fingers.
When you hold this sensor, the simulator will indicate the moisture level
and display a ``||basic::)||`` and when you let go, 
it should display ``||basic: :(||``.

## Step 14
``|Download|`` and test your code.
Congratulations on completing your Automatic Irrigation System! - Go back to the lesson for more activities and extensions.
