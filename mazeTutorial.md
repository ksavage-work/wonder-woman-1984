# Wonder Woman Maze

## Step 1 : Make Wonder Woman @fullscreen

Go to the ``||sprites:Sprites||`` drawer and grab the ``||variables:set mySprite to||`` block. Put this block in the ``||loops:on start||`` loop.
Click the grey box and draw Wonder Woman!
```blocks
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . .
    . . . . . . f f f . . . . . . .
    . . . . f f f 5 f f f . . . . .
    . . . . f f 5 2 5 f f . . . . .
    . . . f f 2 2 2 2 2 f f . . . .
    . . . f f d d d d d f f . . . .
    . . f f f d e d e d f f f . . .
    . . f f f d d d d d f f f . . .
    . f f f f f d d d f f f f f . .
    . f f f f d 2 2 2 d f f f f . .
    . f f . . 5 2 5 2 5 . . f f . .
    . . . . . d 8 8 8 d . . . . . .
    . . . . . . 8 8 8 . . . . . . .
    . . . . . . d . d . . . . . . .
    . . . . . . 2 . 2 . . . . . . .
    . . . . . . . . . . . . . . . .
`, SpriteKind.Player)
```

![WW](https://raw.githubusercontent.com/ksavage-work/wonderw1/master/wonderWoman3.png)

## Step 2 : Let's make Wonder Woman move!

In the ``||controller||`` drawer grab the ``||controller: move mySprite with buttons||`` block. This block will let you conrol Wonder Woman with the arrow keys. Click on the **+** to change your speed. The vx and vy boxes represent her horizontal and vertical speed. Set them both to 150!
```blocks
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . .
    . . . . . . f f f . . . . . . .
    . . . . f f f 5 f f f . . . . .
    . . . . f f 5 2 5 f f . . . . .
    . . . f f 2 2 2 2 2 f f . . . .
    . . . f f d d d d d f f . . . .
    . . f f f d e d e d f f f . . .
    . . f f f d d d d d f f f . . .
    . f f f f f d d d f f f f f . .
    . f f f f d 2 2 2 d f f f f . .
    . f f . . 5 2 5 2 5 . . f f . .
    . . . . . d 8 8 8 d . . . . . .
    . . . . . . 8 8 8 . . . . . . .
    . . . . . . d . d . . . . . . .
    . . . . . . 2 . 2 . . . . . . .
    . . . . . . . . . . . . . . . .
`, SpriteKind.Player)
controller.moveSprite(mySprite, 150, 150)
```

## Step 3 : Create your maze

Now, get the ``||scene: set background color||`` block. Click on the grey box to choose a color. This will end up being the color of the pathway in the maze.
Then, get the ``||scene: set tilemap||`` block. Go to the next step in this tutorial to learn how to draw your maze.
```blocks
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . .
    . . . . . . f f f . . . . . . .
    . . . . f f f 5 f f f . . . . .
    . . . . f f 5 2 5 f f . . . . .
    . . . f f 2 2 2 2 2 f f . . . .
    . . . f f d d d d d f f . . . .
    . . f f f d e d e d f f f . . .
    . . f f f d d d d d f f f . . .
    . f f f f f d d d f f f f f . .
    . f f f f d 2 2 2 d f f f f . .
    . f f . . 5 2 5 2 5 . . f f . .
    . . . . . d 8 8 8 d . . . . . .
    . . . . . . 8 8 8 . . . . . . .
    . . . . . . d . d . . . . . . .
    . . . . . . 2 . 2 . . . . . . .
    . . . . . . . . . . . . . . . .
`, SpriteKind.Player)
controller.moveSprite(mySprite, 150, 150)
scene.setBackgroundColor(11)
tiles.setTilemap(tiles.createTilemap(
            hex`1000100000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000`,
            img`
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
            `,
            [],
            TileScale.Sixteen
        ))
```

## Step 4 : Draw maze

Click on the grey box to choose a color or tile for the walls of your maze, then use the bucket Fill tool to fill in the entire canvas with your color.
Next, use the Erasor tool to draw out the maze. 

![Draw Maze](https://raw.githubusercontent.com/ksavage-work/wonderw1/master/drawMazeBackup.png)

## Step 5 : Create the maze walls

Now that we know what the maze looks like, we need to show the program where the walls of the maze are. 
Go back to your maze in the design space and click on the Wall tool and the Draw tool pencil. 
Using this tool highlight all the walls that Wonder Woman should **NOT** be able to walk through. It should look something like this:

![Draw Walls](https://raw.githubusercontent.com/ksavage-work/wonderw1/master/drawWallsBackup.png)

## Step 5 : Create a Starting Position for Wonder Woman

Go back to your tilemap and choose a new tile from the Gallery to be the start location for Wonder Woman. Place it at the beginning of the maze.
Get the ``||scene: place mySprite on top of||`` block and put it in the ``||loops:on start||`` block. Click on the grey box and select the Start tile that you chose earlier.
Wonder Woman should now start at this location when you play the game.
```blocks
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . .
    . . . . . . f f f . . . . . . .
    . . . . f f f 5 f f f . . . . .
    . . . . f f 5 2 5 f f . . . . .
    . . . f f 2 2 2 2 2 f f . . . .
    . . . f f d d d d d f f . . . .
    . . f f f d e d e d f f f . . .
    . . f f f d d d d d f f f . . .
    . f f f f f d d d f f f f f . .
    . f f f f d 2 2 2 d f f f f . .
    . f f . . 5 2 5 2 5 . . f f . .
    . . . . . d 8 8 8 d . . . . . .
    . . . . . . 8 8 8 . . . . . . .
    . . . . . . d . d . . . . . . .
    . . . . . . 2 . 2 . . . . . . .
    . . . . . . . . . . . . . . . .
`, SpriteKind.Player)
controller.moveSprite(mySprite, 150, 150)
scene.setBackgroundColor(11)
tiles.setTilemap(tiles.createTilemap(

            hex`1000100000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000`,
            img`
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
            `,
            [],
            TileScale.Sixteen
        ))

tiles.placeOnRandomTile(mySprite, sprites.dungeon.stairWest)
```
## Step 6 : Follow the Sprite

Get the ``||scene: camera follow sprite||`` block and add it in the ``||loops:on start||`` block. This makes it so that Wonder Woman will always be on the screen.
```blocks
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . .
    . . . . . . f f f . . . . . . .
    . . . . f f f 5 f f f . . . . .
    . . . . f f 5 2 5 f f . . . . .
    . . . f f 2 2 2 2 2 f f . . . .
    . . . f f d d d d d f f . . . .
    . . f f f d e d e d f f f . . .
    . . f f f d d d d d f f f . . .
    . f f f f f d d d f f f f f . .
    . f f f f d 2 2 2 d f f f f . .
    . f f . . 5 2 5 2 5 . . f f . .
    . . . . . d 8 8 8 d . . . . . .
    . . . . . . 8 8 8 . . . . . . .
    . . . . . . d . d . . . . . . .
    . . . . . . 2 . 2 . . . . . . .
    . . . . . . . . . . . . . . . .
`, SpriteKind.Player)
controller.moveSprite(mySprite, 150, 150)
scene.setBackgroundColor(11)
tiles.setTilemap(tiles.createTilemap(

            hex`1000100000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000`,
            img`
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
            `,
            [],
            TileScale.Sixteen
        ))

tiles.placeOnRandomTile(mySprite, sprites.dungeon.stairWest)
scene.cameraFollowSprite(mySprite)
```
## Step 7 : Create End Position 
Go back to your tilemap and choose a new tile from the Gallery to be the end location of the maze. Place it where you want the end of the maze to be.
Now, drag a ``||scene: on sprite of kind overlaps||`` block into the workspace. This will **NOT** go into the ``||loops:on start||`` block.
Click on the grey tile and select the End tile that you chose.
Get a ``||game: game over||`` block and put it inside the ``||scene: on sprite of kind overlaps||`` block. Switch to **WIN** .

Now, when Wonder Woman overlaps this tile, she'll get out of the maze and win the game!

```blocks
scene.onOverlapTile(SpriteKind.Player, sprites.dungeon.stairLarge, function (sprite, location) {
    game.over(true)
})
```
![End Position](https://raw.githubusercontent.com/ksavage-work/wonderw1/master/endPosition.png)

## Step 8 : Finally, add a countdown timer!

Now let's add a timer to make the maze a bit harder! Get a ``||info: start countdown||`` block and put it inside the ``||loops:on start||`` block. Change the amount of time to 20 seconds.
```blocks
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . .
    . . . . . . f f f . . . . . . .
    . . . . f f f 5 f f f . . . . .
    . . . . f f 5 2 5 f f . . . . .
    . . . f f 2 2 2 2 2 f f . . . .
    . . . f f d d d d d f f . . . .
    . . f f f d e d e d f f f . . .
    . . f f f d d d d d f f f . . .
    . f f f f f d d d f f f f f . .
    . f f f f d 2 2 2 d f f f f . .
    . f f . . 5 2 5 2 5 . . f f . .
    . . . . . d 8 8 8 d . . . . . .
    . . . . . . 8 8 8 . . . . . . .
    . . . . . . d . d . . . . . . .
    . . . . . . 2 . 2 . . . . . . .
    . . . . . . . . . . . . . . . .
`, SpriteKind.Player)
controller.moveSprite(mySprite, 150, 150)
scene.setBackgroundColor(11)
tiles.setTilemap(tiles.createTilemap(

            hex`1000100000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000`,
            img`
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
                . . . . . . . . . . . . . . . .
            `,
            [],
            TileScale.Sixteen
        ))

tiles.placeOnRandomTile(mySprite, sprites.dungeon.stairWest)
scene.cameraFollowSprite(mySprite)
info.startCountdown(20)
```

## Step 9 @unplugged

[Click here to add items for Wonder Woman to collect!](#recipe:https://github.com/ksavage-work/wonderw1/artifacts)

![Add Artifacts](https://raw.githubusercontent.com/ksavage-work/wonderw1/master/artifactPreview.png)
