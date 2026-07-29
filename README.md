 # My First Scene

## Introduction @showdialog

Every game starts with a **scene** — a background, and at least one **sprite** to put on top of it.

The blocks in your ``||loops(noclick):on start||`` run in order, top to bottom. That order is called **sequencing** — and sometimes it changes what your game looks like, and sometimes it doesn't. You'll test both in this tutorial.

## {Step 1}

**Add a background**

- :tree: Open the ``||scene:Scene||`` drawer and drag <br/>
``||scene:set background image to [ ]||`` <br/>
into the empty ``||loops(noclick):on start||`` block already in your workspace.

- :mouse pointer: Click the empty square in the block to open the **Image Editor**. Switch to the **Gallery** tab and pick a background, or draw your own. Click **Done** when you're finished.

~hint What's a scene? 🤷

---

The **scene** is everything that shows up behind your sprites — the sky, the ground, the walls of a maze. Setting a background image is the fastest way to give your game a setting.

hint~

#### ~ tutorialhint
```blocks
// @highlight
scene.setBackgroundImage(assets.image`background`)
```

## {Step 2}

**Add a sprite**

- :paper plane: Open the ``||sprites:Sprites||`` drawer and drag <br/>
``||variables(sprites):set [mySprite] to sprite [ ] of kind [Player]||`` <br/>
into **the end of** the ``||loops(noclick):on start||`` block, right after the background block.

- :mouse pointer: Click the empty square to open the **Image Editor** again. Draw your own character or pick one from the **Gallery**, then click **Done**.

~hint What's a sprite? 🤷

---

A **sprite** is any character or object in your game that can move, disappear, or interact with other things — your player, an enemy, a coin, anything with its own picture.

hint~

#### ~ tutorialhint
```blocks
scene.setBackgroundImage(assets.image`background`)
// @highlight
let mySprite = sprites.create(img`
`, SpriteKind.Player)
```

## {Step 3}

**Test: does order matter here?**

~hint How do I reorder blocks? 🖱️

---

Grabbing a block always drags it and everything stacked **below** it — never what's above it. So to swap two stacked blocks, always grab the **bottom** one; it's the only one you can pull out by itself.

hint~

- :mouse pointer: Click and drag your sprite block (currently on the bottom) straight up and away from the stack to detach it.

- :mouse pointer: Drag it back and drop it right under the ``||loops(noclick):on start||`` hat, above the background block. It should snap into first place and push the background block down below it.

- :binoculars: Check the game window.

~hint What did you notice? 🤔

---

Nothing changed! The background always sits on the very back layer of the scene no matter when you set it, so swapping these two blocks doesn't affect what you see.

Not every pair of blocks behaves like this — try the next step to see one that does.

hint~

- :mouse pointer: Using the same technique, drag the background block (now on the bottom) back above the sprite block, so your scene matches Step 2 again.

## {Step 4}

**Add a second sprite**

- :paper plane: Open ``||sprites:Sprites||`` again and drag another <br/>
``||variables(sprites):set [sprite2] to sprite [ ] of kind [Enemy]||`` <br/>
into **the end of** the ``||loops(noclick):on start||`` block, after ``mySprite``.

- :mouse pointer: Draw a small, simple shape for this one — a star or a hat works well. Don't worry about moving it; new sprites appear in the center of the screen, right on top of ``mySprite``.

- :binoculars: Check the game window. One sprite should be sitting on top of the other.

#### ~ tutorialhint
```blocks
scene.setBackgroundImage(assets.image`background`)
let mySprite = sprites.create(img`
`, SpriteKind.Player)
// @highlight
let sprite2 = sprites.create(img`
`, SpriteKind.Enemy)
```

## {Step 5}

**Now swap the order**

- :mouse pointer: Using the same technique from Step 3 — grab the **bottom** block first and pull it out — swap ``sprite2`` so it's above ``mySprite`` instead of below it. Check the game window again.

~hint What changed this time? 👀

---

This time, order **does** matter! When two sprites overlap, MakeCode draws the one created **later** on top. Whichever "set sprite" block comes last in your sequence is the one that ends up visible.

This is different from Step 3 — the background isn't a sprite, so it's never part of this stacking order. But sprites always stack in the order they're created.

hint~

## {Step 6}

**Add comments**

Put ``sprite2``'s block back in the order you want (whichever sprite should show on top goes last). Now leave yourself a note on **every** block in your stack — right now you're just getting started, so you'll comment almost everything.

- :mouse pointer: Right-click the ``||loops(noclick):on start||`` hat block itself and choose **Add Comment**. Type something like *"Builds my scene once when the game starts."*

- :mouse pointer: Right-click the background block and add a comment, something like *"Background — always stays on the back layer no matter where this block sits."*

- :mouse pointer: Right-click ``mySprite``'s block and add a comment describing its purpose, like *"The player's character."*

- :mouse pointer: Right-click ``sprite2``'s block and add a comment, like *"This has to come after mySprite so it shows up on top."*

- :mouse pointer: Click the small speech-bubble icon on any block any time to show or hide its note.

~hint Why bother writing comments? 💬

---

Comments don't change how your code runs — the computer ignores them completely. They're notes for **you** (and anyone else reading your code later). Right now you're commenting almost every block because these ideas are brand new. Later on, you'll comment less often — mostly just the big outer blocks (like on start) and anything that introduces a new idea.

hint~

## {Step 7}

- :binoculars: Check the game window one more time. You should see a background with two sprites stacked in the order you chose. Your comments won't show up here — comments stay attached to their blocks in your workspace, not in the game itself.

## {Finale}

**Nice work!**

You've built a scene with a background and two sprites — and you've seen sequencing in action: some blocks don't care what order they're in, but others (like overlapping sprites) absolutely do. Comments help you remember which is which.

Before you click Done, try experimenting: swap in different backgrounds and sprites, add a third sprite, or try other orderings and see what changes.

Click **Done** when you're ready to save your project.



> Open this page at [https://lesleyplangdon.github.io/introprogrammingblockstap101/](https://lesleyplangdon.github.io/introprogrammingblockstap101/)

## Use as Extension

This repository can be added as an **extension** in MakeCode.

* open [https://arcade.makecode.com/](https://arcade.makecode.com/)
* click on **New Project**
* click on **Extensions** under the gearwheel menu
* search for **https://github.com/lesleyplangdon/introprogrammingblockstap101** and import

## Edit this project

To edit this repository in MakeCode.

* open [https://arcade.makecode.com/](https://arcade.makecode.com/)
* click on **Import** then click on **Import URL**
* paste **https://github.com/lesleyplangdon/introprogrammingblockstap101** and click import

#### Metadata (used for search, rendering)

* for PXT/arcade
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
