
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
