# Guide to Making Visual Novels - Part 2
### 🌊 Diving into adding music, changing up the GUI, and more 🎨

![alt text](https://github.com/lovebirdsnest/Guide-to-Making-Visual-Novels/blob/master/images/home.png "Example visual novel")

Now that we have learned the basics in our [previous tutorial](https://blog.prototypr.io/guide-to-making-visual-novels-e86e5fc835b7), we're ready to move on to some of the more complicated things Ren'Py can do. Note: You can always checkout the [GitHub page](https://github.com/lovebirdsnest/From-Here-to-You) of my game if you don't understand how to alter something and you can use the assets from that game to practice with if you wish.

#### 🎵 Adding Music to Your Game

1. It's easy to add music to your game. The audio file types that are supported by Ren'Py are: Opus, Oggs Vorbis, MP3, and WAV. So as long as your music is saved as one of these types, you're good to go. Place your music file in the `game` main folder or create a new folder in the `game` main folder and call it `music` (this is what I usually do to keep things organized). To play the song in your game, simply write `play music "music/[name of file with extension]"`. If you want the song to loop, you can get it to do so by typing `play music "<loop 0>music/[name of file with extension]"` instead.
2. To fade in the music, you can write `fadein [time]` afterwards to allow for a more gradual start to a song.
3. To stop the music, simply write `stop sound` and to have the music fadeout, write `stop music fadeout [time]`. <br> An example of playing a song in Ren'Py with the file name of `friends.ogg` (not that the file is located in a folder called `music` in this example): `play music "<loop 0>music/friends.ogg" fadein 2.0`

#### 🔠 Changing the Game Font

1. The font you use in your game can change the feel of it drastically. It's quite easy to change which font your game has though so worry not. The font I will be using as an example is called `BrownBagLunch.ttf` so don't get confused if you see it. Download your font from online and then place the .tff file in your main `game` folder.
2. Open the file called `gui.rpy` and look for a line that says `define gui.text_font = `. Change whatever is after the equals sign to the name of the font you put in the `game` folder, complete with the extension at the end. You can change the font for the options underneath as well if you wish or change them to even different fonts. Right below the fonts, you can also change the font size if you wish.
![alt text](https://github.com/lovebirdsnest/Guide-to-Making-Visual-Novels-2/blob/master/images/2.png "Changing the font of your game")


#### 🎨 Changing the game GUI

1. There's so many things you can alter about your game that it would difficult to go over all of them but I'll explain how to do some things that I do all the time when making games to make them look better.
2. One thing I do a lot is get rid of the side bar overlay on the left side of the `Main Menu` because it usually covers my art and looks a little out of place in the games I make. What's outlined in red is what I'm talking about: <br>![alt text](https://github.com/lovebirdsnest/Guide-to-Making-Visual-Novels-2/blob/master/images/3.png "Getting rid of side bar")
3. To get rid of this, I usually just open the file `gui/overlay/main_menu.png` in Photoshop. There I erase/delete everything in the image and save again. Ta-da! The side bar overlay is gone. **Note:** You'll also notice the files `confirm.png` and `game_menu.png` in the folder. You can alter these too any way you wish.
<br> How the main menu looks afterwards:
![alt text](https://github.com/lovebirdsnest/Guide-to-Making-Visual-Novels-2/blob/master/images/4.png "Getting rid of side bar")
4. Next, I usually always change how the dialogue box looks.To do this, go to the main `game/gui` folder and open the `textbox.png` file in Photoshop. Then change it to whatever you want. I usually just make an oval shape with a border like so:
![alt text](https://github.com/lovebirdsnest/Guide-to-Making-Visual-Novels-2/blob/master/images/5.png "Changing dialogue box")
5. Getting rid of the navigation items at the bottom of the screen. You may not always want to do this but I really wanted a way to get rid of the navigation window at the bottom because it got in the way of my dialogue box and such. I also didn't have a need for them so I decided to get rid of them. To do this, you have to go into the `screens.rpy` file and find the line that says `default quick_menu = True`. Change the `True` to `False` to get rid of the menu at the bottom.
![alt text](https://github.com/lovebirdsnest/Guide-to-Making-Visual-Novels-2/blob/master/images/6.png "Getting rid of the quick menu")
6. To continue, you could also change the rest of the image files in the `gui` folder to your liking. This will really make your game look more cohesive and like it's of a certain style.

#### 🖼 Animating Your Characters

1. Sometimes you might want to animate some of your characters in a game. Personally, I don't do this much but it's good to know how. Animating in Ren'Py is perhaps a little different than you would expect. When I first started, I thought that perhaps I could put in a gif or something but that's not the case. Each frame of the animation is a .png/jpeg in the `images` folder that are put in a sequence by Ren'Py.
2.  Once you have the images you want in your animation saved in the `images` folder, all you have to do is create a new `image` definition in Ren'Py. Then put the images you want in a sequence seperated by pause times like this:
```
image kiwi moving:
        "kiwi silly.png"
        pause 1.0
        "kiwi blush.png"
        pause 1.0
        repeat
```
3. The `repeat` at the bottom shows Ren'Py that you want the image to keep looping and going through the sequence until another expression is called on that character or it's hidden.

#### 👾 Exporting Your Game

1. Exporting your game is pretty straight-forward. On the Ren'Py application, press `Build Distributions` then press which operating systems you want to build for. Then simpl ny press `Build` and Ren'Py will package your game into executable file/s. If for some reason the build fails, it's probably because your files are named the wrong (see the first guide for Ren'Py naming conventions). If it's not that, try restarting the application/Ren'Py.


Alright, that finishes this second guide to Ren'Py! It's probably also the final guide I make on Ren'Py since it's all you really need to make a nice-looking game. Keep creating & having fun 🎮
