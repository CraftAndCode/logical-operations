# Logical operations

```package
core
radio
microphone
```

```template
basic.forever(function () {
    
})
```

```blocks
basic.forever(function () {
    
})
```
## Step 0 @showDialog
Hello! Today we'll learn how to give the Micro:bit more specific conditions to run the code.
## Step 1 @showDialog
### Logical AND
Sometimes we need a set of actions to be performed when several conditions are met at the same time.
  
For example:  
- If there are eggs `AND` there is bacon in the fridge, make breakfast.
- If homework is done `AND` it's not bedtime, play video games.
  
You can make the Micro:bit follow the same logic using the ``||logic.and||`` block from the ``||logic.logic||`` category.
  
For example:
- If the `A` button is pressed `AND` the `B` button is pressed, play a sound.
```block
if (input.buttonIsPressed(Button.A) && input.buttonIsPressed(Button.B)) {
    soundExpression.giggle.playUntilDone()
})
```

## Step 2 @showDialog
### Logical AND
Note that you can use multiple ``||logic.and||`` blocks to combine as many conditions as you want.
```blocks
if (input.buttonIsPressed(Button.A) && input.buttonIsPressed(Button.B) && input.logoIsPressed()) {
    basic.showIcon(IconNames.Yes)
    }
```
## Step 3 @showDialog
### Logical AND
The ``||logic.and||`` blocks are also useful when you want your code to start when a specific combination of sensor values happens.
```block
if (input.temperature() > 30 && input.lightLevel() > 200) {
        basic.showString("It is warm and bright")
    }
```
## Step 4 @showHint
### Logical AND
Let's assemble an example of using the ``||logic.and||`` block!
Here, the Micro:bit displays a happy face only if  both buttons are pressed. Download this code to the Micro:bit and check it for yourself!
```blocks
basic.forever(function () {
    if (input.buttonIsPressed(Button.A) && input.buttonIsPressed(Button.B)) {
        basic.showIcon(IconNames.Yes)
    } else {
        basic.clearScreen()
    }
})
```
## Step 5 @showDialog
### Logical OR
Logical ``||logic.or||`` is used when an action should be performed on either of the conditions.
  
For example:
- If there are no eggs `OR` no bacon in the fridge, go to the shop.
- If it's Sunday `OR` it's Saturday, don't go to school.
  
- If any button is pressed, play a sound.

```block
if (input.buttonIsPressed(Button.A) || input.buttonIsPressed(Button.B)) {
    soundExpression.giggle.playUntilDone()
})
```
## Step 6 @showHint
### Logical OR
In your code, replace ``||logic.and||`` with ``||logic.or||``. Download your code to the Micro:bit. Can you see what's changed?
```blocks
basic.forever(function () {
    if (input.buttonIsPressed(Button.A) || input.buttonIsPressed(Button.B)) {
        basic.showIcon(IconNames.Yes)
    } else {
        basic.clearScreen()
    }
})
```
## Step 7 @showDialog
### Logical NOT
It's easy for a human brain to understand the difference between two opposite conditions.
  
For example:
- A green traffic light and `NOT` a green traffic light
- A homework assignment that is done and homework that is `NOT`done.
  
To tell the computer to wait for a condition that is the opposite of something, we use a ``||logic.not||`` block.
  
For example:
- If a button is `NOT` pressed, show a heart icon, else show nothing.
```block
 if (!(input.buttonIsPressed(Button.A))) {
        basic.showIcon(IconNames.Heart)
    } else {
        basic.clearScreen()
    }
```
## Step 8 @showHint
### Logical NOT
Using these three logical operations, you can construct a condition that's as complex as you want. This code, for example, makes the Micro:bit show the sun picture only if it is bright and no buttons are pressed.
```blocks
basic.forever(function () {
    if (input.lightLevel() > 200 && !(input.buttonIsPressed(Button.A) || input.buttonIsPressed(Button.B))) {
        basic.showLeds(`
            # . # . #
            . # # # .
            # # # # #
            . # # # .
            # . # . #
            `)
    } else {
        basic.clearScreen()
    }
})
```

## Step 9
### Now it's your turn!
Here's a challenge for you! Write a program that does the following:
- If the `A` button is not pressed, show an icon, otherwise show nothing.
- If the `A` button and the sensor are pressed, show some text, otherwise show nothing
- If it's dark or cold, play some sound.

## Step 10 @showDialog
### Answers: Do it yourself
This is one of the answers to the challenge. Does your code look like this, or did you find another way to complete it?
```blocks
basic.forever(function () {
    if (!(input.buttonIsPressed(Button.A))) {
        basic.showIcon(IconNames.Heart)
    } else {
        basic.clearScreen()
    }
    if (input.buttonIsPressed(Button.A) && input.logoIsPressed()) {
        basic.showString("Hello!")
    } else {
        basic.clearScreen()
    if (input.lightLevel() < 50 || input.temperature() < 10) {
        soundExpression.giggle.playUntilDone()
    }
})
```

## Step 11
You've completed the challenge - excellent! Now you know about using `AND`, `OR` and `NOT` blocks and you can use them in your own programs.
