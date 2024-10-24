
# Pixel Pad Documentation

Pixelpad is a good game engine but lacks suffecient documentation so this readme
will account for that. 

## Custom/Game Class and Sprites
Custom Classes contain the *self.* while the Game Class contains initalizations of custom classes. Example
```python
# Custom class
self.sprite = sprite("Sprite File Location/Name") # Sets the class to a specific image
self.x = 100 # Moves the sprite to x = 100
self.y = 200 # Moves the sprite to y = 200
self.scaleX = 0.5 # Scales the sprites length by 50% (0.5x)
self.scaleY = 2 # Scales the height by 200% (2x)
```
On the other hand, the Game Class calls the custom classes
```python

water = Water() # Instead of self. we use class_var = Class()
sand = Sand()
water.x = 100 # Does the same thing as self.x in the Water Custom Class
water.y = 200 # Does the same thing as self.y in the Water Custom Class
sand.scaleX = 2 # Does the same thing as self.scalex in the Water Custom Class
sand.scaleX = 3 # Does the same thing as self.scaleY in the Water Custom Class
```
For navigation of a character, within the custom classes game loop:
```python
if key_is_pressed("w"):
    self.y += 5
if key_is_pressed("s"):
    self.y -= 5
if key_is_pressed("a"):
    self.x -= 5
if key_is_pressed("d"):
    self.x += 5
```

## Managing multiple sprites

When there are multiple sprites for example in a grid, it makes modifying any one of them extremely difficult. 

When calling in a new sprite, add it to a sprite list. 

```python
self.waterList = []
for i in range(-10,10):
    for j in range(-10,10):
        self.water = Water()
        self.water.x = i*30
        self.water.y = j*30
        self.waterList.append(self.water)
```

Then to modify any or specific sprite, use the index method with lists. Within the game loop
```python
import random

temp = random.randint(0,100)
posx = random.randint(0,19)
posy = random.randint(0,19)
randomWater = random.randint(0,19*19)
self.waterList[randomWater].tempature = temp
```
Within the water class
```python
self.sprite = sprite("Water.png")
self.scaleX = 0.2
self.scaleY = 0.2
self.tempature = 25
```
To modify any data within the sprite itself such as image, use the sprite loop to update image based on tempature for example
```python
if self.tempature < 50:
    self.sprite = sprite("Water.png")
if self.tempature >= 50:
    self.sprite = sprite("ehs.png")
```


