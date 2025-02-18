# Far from home

# Table of contents
1. [Introduction](#introduction)
    1. [About the game](#about)
    2. [Dev notes](#devnotes)
    3. [Developers](#developers)
2. [Gameplay](#gameplay)
3. [Build](#build)

# Introduction <a name="introduction"></a>

## About the game <a name="about"></a>
You are playing on behalf of the cat, who got lost in the woods. The forest you 
got into is not that simple - in some trees there are hidden portals which
can bring you home. Ofcourse you are not alone in that forest: there are other 
cats too (and not only them). Your main goal is to find them and bring into your
pack (group of cats), because only this way you can send them to different trees in order to find portals. You
will win the game, when you manage to send all lost kittens back to their homes 
and stay alive during the process.

## Dev notes <a name="devnotes"></a>

The whole project is written on C++ according to Google Code Style.
Code checked by cpplint.

## Developers <a name="developers"></a>
Game was designed by **"Bez-bab"** team (@sherri-ice, @yanapush, @shine-bright-like-a-diamand, @polimakruseva) as university project.

## Gameplay <a name="gameplay"></a>
### Menu

![](https://github.com/polimakruseva/far-from-home/blob/main/images/markdown/Screenshot%20from%202021-10-28%2009-00-13.png)

To pause the game and enter menu press 'Space'.

### Kittens
#### Main kitten:

![](https://github.com/polimakruseva/far-from-home/blob/main/images/markdown/kitten.jpg)

You can navigate your cat using keys _WASD._

#### Collect kittens:


![](https://github.com/polimakruseva/far-from-home/blob/main/images/markdown/kittens.jpg)


You can't see it while playing, but your main cat actually has special visibility
area:

![](https://github.com/polimakruseva/far-from-home/blob/main/images/markdown/radius.jpg)

Inner circle defines trigger border for cats: if kitten came up close to this 
area then it will be added to the _group_.

Outer circle defines _the group border_: kittens can move freely inside the group 
border.

If kitten gone out of the group border _it leaves the group._

Also borders of these areas grow depending on the number of cats in your pack. 

### Health
Cat has health. Indicator is at the top of the screen:

![](https://github.com/polimakruseva/far-from-home/blob/main/images/markdown/full.jpg)

Health decreases during game process. You will get the first warning when only 40% 
of health is left:

![](https://github.com/polimakruseva/far-from-home/blob/main/images/markdown/middle_health.jpg)


 If you've got only 15% of health left, you will get last warning and all cats in
 your group will leave you:

![](https://github.com/polimakruseva/far-from-home/blob/main/images/markdown/no_healtj.jpg)

If no health left you will die :(

![](https://github.com/polimakruseva/far-from-home/blob/main/images/markdown/die.jpg)


### Food
To increase your health you can eat some delicious food! Be aware: with time
some food can be spoiled and actually decrease your health. Don't worry fresh 
food is also generated with time.

![](https://github.com/polimakruseva/far-from-home/blob/main/images/markdown/food.jpg)

### Enemies
#### Dog

![](https://github.com/polimakruseva/far-from-home/blob/main/images/markdown/dog.jpg)

Despite it looks so cute, it's your enemy!

If dog detects you, it will attack. 
Dog attack causes health decreasing. If the dog attacks some cat in your group, 
you will lose this cat.
And if the dog attacked the main cat, all group cats will get scared and will 
run away!

### Portals

They are hidden inside the trees. To send your cat on search click on the tree.

![](https://github.com/polimakruseva/far-from-home/blob/main/images/markdown/portak.jpg)

### Map

[comment]: <> (By pressing key `Q` and)

You can zoom in and zoom out the map using keys 'Q' and 'E'.

# Build <a name="build"></a>

##Required libs:

[Qt 5](https://www.qt.io/ "Qt's homepage")

##  CMakeList
You should specify your _Qt 5_ place:

`set(CMAKE_PREFIX_PATH "~/your/path/to/qt/Qt5/")`

For example:

`set(CMAKE_PREFIX_PATH "~/Qt/5.12.11/gcc_64/lib/cmake/Qt5/")`

Also, you should specify Qt libraries which are used:

`set(REQUIRED_LIBS Core Gui Widgets Multimedia MultimediaWidgets)`

`set(REQUIRED_LIBS_QUALIFIED Qt5::Core Qt5::Gui Qt5::Widget Qt5::Multimedia)`

[CMakeLists.txt Example](https://www.qt.io/ "CMakeLists.txt Example")

