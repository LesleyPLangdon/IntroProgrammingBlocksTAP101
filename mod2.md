# Naming Your Variables

## Introduction @showdialog

Last lesson you built a scene with a background and two sprites — but you gave them plain, default names: ``mySprite`` and ``sprite2``. Those names don't tell you anything about what the sprites actually are.

In this lesson you'll give them real names, and discover that variables can hold more than just sprites — numbers and words too.

```template
let mySprite: Sprite = null
let sprite2: Sprite = null
scene.setBackgroundColor(9)
mySprite = sprites.create(img`
.............ccfff..............
............cddbbf..............
...........cddbbf...............
..........fccbbcf............ccc
....ffffffccccccff.........ccbbc
..ffbbbbbbbbbbbbbcfff.....cdbbc.
ffbbbbbbbbbcbcbbbbcccff..cddbbf.
fbcbbbbbffbbcbcbbbcccccfffdbbf..
fbbb1111ff1bcbcbbbcccccccbbbcf..
.fb11111111bbbbbbcccccccccbccf..
..fccc33cc11bbbbccccccccfffbbcf.
...fc131c111bbbcccccbdbc...fbbf.
....f33c111cbbbfdddddcc.....fbbf
.....ff1111fbdbbfddcc........fff
.......cccccfbdbbfc.............
.............fffff..............
`, SpriteKind.Player)
sprite2 = sprites.create(img`
. . . . . . . . . . . . . . . . 
. . . . . . . c c c c c . . . . 
. . . . . . c d d d d d c . . . 
. . . . . . c c c c c d c . . . 
. . . . . c 4 4 4 4 d c c . . . 
. . . . c d 4 4 4 4 4 1 c . . . 
. . . c 4 4 1 4 4 4 4 4 1 c . . 
. . c 4 4 4 4 1 4 4 4 4 1 c c c 
. c 4 4 4 4 4 1 c c 4 4 1 4 4 c 
. c 4 4 4 4 4 1 4 4 f 4 1 f 4 f 
f 4 4 4 4 f 4 1 c 4 f 4 d f 4 f 
f 4 4 4 4 4 4 1 4 f f 4 f f 4 f 
. f 4 4 4 4 1 4 4 4 4 c b c f f 
. . f f f d 4 4 4 4 c d d c . . 
. . . . . f f f f f c c c . . . 
. . . . . . . . . . . . . . . . 
`, SpriteKind.Enemy)
```

## {Step 1}

**Find your variables**

- :abacus: Open the ``||variables:Variables||`` drawer. You should see ``mySprite`` and ``sprite2`` already listed there.

~hint Wait, sprites are variables? 🤔

---

Yes! Back in Module 1, ``||variables(sprites):set [mySprite] to sprite [ ] of kind [Player]||`` created a variable named ``mySprite`` and stored your sprite inside it. Any time you see a **set** block, you're looking at a variable being filled with something — a sprite, a number, or a word.

hint~

## {Step 2}

**Rename mySprite**

- :mouse pointer: Click the down-arrow on the ``mySprite`` block and choose **Rename variable...**. Rename it to ``hero``.

~hint Will this break my code? 🤷

---

No — renaming a variable only changes its label. Every block that used ``mySprite`` updates automatically to say ``hero`` instead, and your code runs exactly the same as before.

hint~

## {Step 3}

**Rename sprite2**

- :mouse pointer: Using the same steps, rename ``sprite2`` to ``target``.

- :binoculars: Check the game window — nothing should look different. Only the names changed, not the code.

## {Step 4}

**Create a number variable**

- :abacus: Click ``||variables:Variables||`` and choose **Make a Variable...**. Name it ``pointsPerCatch`` and set it to ``1``.

- :id card: Open ``||info:Info||`` and drag ``||info:change score by [1]||`` into **the end of** the ``||loops(noclick):on start||`` block. Replace the number with your ``pointsPerCatch`` variable.

- :binoculars: Check the game window — a score should appear, already at 1!

~hint Why use a variable instead of just typing 1? 🤔

---

You could type ``1`` directly, and it would work exactly the same right now. But if you decide later that catching a target should be worth 5 points instead of 1, you only have to change it in **one place** — wherever ``pointsPerCatch`` is set — instead of hunting down every block that uses that number.

hint~

#### ~ tutorialhint
```blocks
let pointsPerCatch = 1
info.changeScoreBy(pointsPerCatch)
```

## {Step 5}

**Start a countdown**

- :id card: From ``||info:Info||``, drag ``||info:start countdown [3] (s)||`` into **the end of** the ``||loops(noclick):on start||`` block.

- :binoculars: Check the game window. A timer should start counting down.

Right now this countdown just runs once when the game starts, and nothing happens when it ends — that's fine for today. Next lesson, once you've learned to move your hero and detect when it touches the target, you'll move this block (and the score block) into an event that runs every time they touch.

## {Step 6}

**Create a variable for your player's name**

- :abacus: Click ``||variables:Variables||`` and **Make a Variable...**. Name it ``playerName``.

- :mouse pointer: Open ``||text:Text||`` and drag the ``||text:" "||`` block into ``playerName``'s value slot. Type your own name (or any name you like) inside the quotes.

## {Step 7}

**Create a variable for the target's name**

- :abacus: Click ``||variables:Variables||`` and **Make a Variable...** again. Name it ``targetType``.

- :mouse pointer: Open ``||text:Text||`` and drag another ``||text:" "||`` block into ``targetType``'s value slot. Type ``targets`` inside the quotes (or something more specific, like ``fish`` or ``burgers``, depending on your game).

~hint Why not just reuse "target"? 🤔

---

Good question if you were wondering — your ``target`` variable holds an actual **sprite**: a picture that moves around your game. That's a different type of data than a word. So we need a separate variable, ``targetType``, just to hold the text itself.

hint~

## {Step 8}

**Combine text with Create text with**

- :mouse pointer: Open ``||text:Text||`` and find the **Create text with** block. Drag it out.

- :mouse pointer: Click the small blue gear on the block. You'll need **five** slots total this time — drag in extra slots until you have five.

- :mouse pointer: Fill the five slots with: the text ``"Get ready, "``, your ``playerName`` variable, the text ``"! Catch as many "``, your ``targetType`` variable, and the text ``" as you can!"``.

- :abacus: Create one more variable named ``instructions``, and set it to this whole combined block.

#### ~ tutorialhint
```blocks
let playerName = "Alex"
let targetType = "targets"
let instructions = "Get ready, " + playerName + "! Catch as many " + targetType + " as you can!"
```

## {Step 9}

**Show your instructions**

- :video game: Open ``||game:Game||`` and drag ``||game:splash [ ]||`` into **the end of** the ``||loops(noclick):on start||`` block, after everything else.

- :mouse pointer: Plug your ``instructions`` variable into it instead of typing new text.

- :binoculars: Check the game window — your personalized instructions should pop up on top of your finished scene!

#### ~ tutorialhint
```blocks
let playerName = "Alex"
let targetType = "targets"
let instructions = "Get ready, " + playerName + "! Catch as many " + targetType + " as you can!"
// @highlight
game.splash(instructions)
```

## {Finale}

**Nice work!**

You gave your sprite variables real names, and created three brand-new variables of your own — a number and two pieces of text — each doing a real job in your game: showing a score and building a personalized message out of smaller pieces of text.

Before you click Done, try experimenting: change ``pointsPerCatch`` to a different number, or edit ``playerName`` and ``targetType`` and watch the splash message update to match.

Click **Done** when you're ready to save your project.
