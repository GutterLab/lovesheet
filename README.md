# lovesheet.lua
Parses texture packer xml files to build quads for sprite sheets in Love2d.

# Usage
You need some sort of xml file from a texture packer. I use https://github.com/odrick/free-tex-packer. At the moment this script doesn't support rotation. It only parses properties named: n x y w h . It also parses the width and height of the entire sprite sheet as long as the properties exist. The script expects output similar to free-tex-packer's default xml output. 

```
---Actual code might be different for love2d. I've only used it through http://castle.games and requires work differently.
ls = require("lovesheet")

--This expects a loaded image and the xml file as a string.
ls.LoadSpriteSheet(love.graphics.newImage("sprites.png"), require("sprites"))

--spritename here would be the filename of the sprite within the sprite sheet without the extension. The method returns the spritesheet as an image and the quad for the sprite.
local d, q = ls.GetDraw("spritename")

--call draw as usual.
love.graphics.draw(d, q, x, y)
```

# Limitations
A lot, at the moment it only supports a single sprite sheet.