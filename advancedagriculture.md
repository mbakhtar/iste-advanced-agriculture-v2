# Automatic Irrigation System
```package
fwd-edu-breakout=github:climate-action-kits/pxt-fwd-edu/fwd-breakout
ledRing=github:climate-action-kits/pxt-fwd-edu
soilMoisture=github:climate-action-kits/pxt-fwd-edu
```
## @showdialog
Welcome to Automatic Irrigation System
![built project](https://raw.githubusercontent.com/mbakhtar/iste-advanced-agriculture-v2/master/project%20-%20watering%20plant.png)

## Step 1 @showdialog
Plug your USB cable into the micro:bit and insert it into the 
Climate Action Kit board. 
![breakout board](https://raw.githubusercontent.com/mbakhtar/wind-turbine-lesson-tutorial/master/breakout-resized.png)

## Step 2 @showhint
Click three dots besides ``|Download|`` button and follow the steps to pair your micro:bit.
![pair gif](https://raw.githubusercontent.com/mbakhtar/iste-electric-vehicle-v1/master/pair%20microbit-280x203.gif)

## Step 3
Click ``||fwdSensors:Sensors||`` drag and drop ``||fwdSensors:set all ledRing LEDs to 10||`` block inside ``||basic:forever||`` loop.
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(10)
    )}
```
## Step 4
Click ``||logic: Logic||`` drag and drop ``||logic:If then Else||``
block under ``||fwdSensors:set all ledRing LEDs to 10||`` block.
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
Click ``||fwdSensors:Sensors||`` drag and drop ``||fwdSensors:is soilMoisture1 moisture level over 5%||`` 
to replace ``||logic:true||`` condition of ``||logic:if then else||`` block.
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
Click ``||basic:basic||`` drag and drop ``||basic:show icon||`` block inside ``||logic:if then||`` condition. 
Select ``||basic: :)||`` icon.
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
Click ``||basic:basic||`` drag and drop ``||basic:show icon||`` block inside ``||logic:else||`` condition.
Select ``||basic: :(||`` icon.
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(10)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(5, fwdSensors.thresholdDirection.over)) {
          basic.showIcon(IconNames.Happy)} 
    else {
        basic.showIcon(IconNames.Sad)}
        )}
```
## Step 8
Click ``||fwdMotors:Motors||`` drag and drop ``||fwdMotors:run pump for 500||`` under 
 ``||basic: :(||`` icon. 
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(10)
    if (fwdSensors.soilMoisture1.fwdIsMoistureLevelPastThreshold(50, fwdSensors.thresholdDirection.over)) {
        basic.showIcon(IconNames.Happy)
        } else {
        basic.showIcon(IconNames.Sad)
        fwdMotors.pump.fwdTimedRun(100)
        }
})
```
## Step 9
Click ``||basic:basic||`` drag and drop ``||basic:pause (ms) 100||`` block under ``||fwdMotors:run pump for 500||`` block. 
Change the ``||basic:100||`` to ``||basic:500||``
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(10)
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
## Step 10
Click ``||basic:basic||`` drag and drop ``||basic:clear screen||`` 
block under ``||basic:pause (ms) 500||`` block.
```blocks
basic.forever(function () {
    fwdSensors.ledRing.fwdSetAllPixelsColour(10)
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
``|Download|`` and test your code.
Congratulations on completing your Automatic Irrigation System! - Go back to the lesson for more activities and extensions.
