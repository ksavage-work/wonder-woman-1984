# Wonder Woman Maze

## Introduction @unplugged

![Game animation](https://raw.githubusercontent.com/ksavage-work/wonder-woman-1984/master/wwSplash.gif)
Hey, let's make a game where Wonder Woman must find the way out of a tricky maze! In that maze, she can collect
artifacts to gain points, but also needs to avoid her enemies that will steal points. 

## Step 1 : Make Wonder Woman @fullscreen

Open the ``||sprites:Sprites||`` Toolbox drawer and grab the ``||variables:set mySprite to||`` block. Drop this block in the ``||loops:on start||`` block.
In the ``||variables:set mySprite to||`` block, click the grey box and draw Wonder Woman!
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

![WW](https://raw.githubusercontent.com/ksavage-work/wonder-woman-1984/master/wonderWoman3.png)

## Step 2 : Let's make Wonder Woman move!

In the ``||controller||`` drawer grab the ``||controller: move mySprite with buttons||`` block. 
This block will let you conrol Wonder Woman with the joystick or the arrow keys. 
Click on the **+** to change your speed. The vx and vy boxes represent her horizontal and vertical speed. 
Set them both to 150! Now try moving Wonder Woman around the screen.
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

From the Scene Toolbox drawer, get the ``||scene: set background color||`` block and drop it into the On Start block. Click on the grey oval to choose a color. This will end up being the color of the pathway in the maze.
Also from the Scene Toolbox drawer, drag and drop a ``||scene: set tilemap||`` block. Go to the next step in this tutorial to learn how to draw your maze.
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

In the Set Tilemap block, click on the grey box to choose a color or tile for the walls of your maze, then use the bucket Fill tool to fill in the entire canvas with the tile you selected.
Next, use the Erasor tool to draw the path for the maze. 

![Draw Maze](https://raw.githubusercontent.com/ksavage-work/wonder-woman-1984/master/drawMaze.gif)

## Step 5 : Create the maze walls

Now that we know what the maze looks like, we need to show the program where the walls of the maze are. 
In the Tilemap Editor, click on the red Wall icon, then draw the walls around your Maze math. 
Using this tool highlight all the walls that Wonder Woman should **NOT** be able to walk through.

![Draw Walls](https://raw.githubusercontent.com/ksavage-work/wonder-woman-1984/master/drawWalls.gif)

## Step 6 : Create a Starting Position for Wonder Woman

In the Tilemap Editor, choose a new tile from the Gallery to be the start location for Wonder Woman. Place it at the beginning of the maze.
Get the ``||scene: place mySprite on top of||`` block and put it in the ``||loops:on start||`` block. Click on the checkered box and select the Start tile that you chose earlier.
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
## Step 7 : Follow the Sprite

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
## Step 8 : Create End Position 
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
![End Position](https://raw.githubusercontent.com/ksavage-work/wonder-woman-1984/master/endPosition.png)

## Step 9 : Finally, add a countdown timer!

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

## Step 10 @unplugged

[Click here to add items for Wonder Woman to collect!](#recipe:https://github.com/ksavage-work/wonder-woman-1984/artifactTutorial)

![Add Artifacts](https://raw.githubusercontent.com/ksavage-work/wonder-woman-1984/master/artifactPreview.png)
