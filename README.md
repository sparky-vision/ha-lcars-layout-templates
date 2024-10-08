# ha-lcars-layout-templates
Some templates for HA-LCARS

Here are some grid layouts for your Home Assistant HA-LCARS needs.

In messing around with Home Assistant, I ran across the delightful HA-LCARS theme. Now, the two people who know anything about me know that I'm 1) a giant Star Trek nerd with an encyclopedic knowledge of most of the franchise from TNG onward and 2) a general home automation nerd. Naturally, I was drawn to the intersection of a real and imagined future with Home Assistant and theming it to look like Michael and Denise Okuda's amazing work designing the user interface of the fuuuutreeeee in Star Trek: TNG. It's a very recognizable interface, and I - along with lots of others - think the general use of color and shapes seems very usable. Anyhoo. In setting about to recreate some of the layouts we see on-screen, I ended up deciding to use lovelace-layout-card grids, which lets you define CSS grids and position things with them. This seems, by *far*, the best way to position things within the HA system. I decided maybe the community could use my snippets, and so, here they are.

To use, install all the dependencies, and then copy / paste from the file you want to use into the yaml editor of your layout.

You WILL have to adjust sizing to make everything align. Right now, most of the elements are not particularly scalable - or they might be, and I'm doing it wrong, I welcome correction on that - but coding something totally self-resizing is beyond my capabilities. So you'll likely need to adjust for your device. The way I get around this is to copy these views and then resize them for a specific device. Since I only have one or two displays in my house for interacting with HA, that's fine for me.

First things first.

<h1>Dependencies</h1>

To use these, you'll need:

Home Assistant, *obviously*.<br>
<a href="https://github.com/th3jesta/ha-lcars">HA-LCARS</a>. The thing that makes this all worth the while.<br>
<a href="https://github.com/thomasloven/lovelace-layout-card">Lovelace Layout Card</a><br>
<a href="https://github.com/snootched/cb-lcars">CB-LCARS". I make a lot of use of snootched's stuff he's written. Note that this project has a lot of its own dependencies, which the layouts don't necessarily require, but which you might find useful.<br><br>

<h1>Installing</h1>

All you need do is copy the yaml file to the yaml editor of the layout you're tring to use.

<h1>Working with grid layouts</h1>

Here's where things get fun. If you don't read anything else, read this section.

CSS grids are just that - grids. Take a look.

```
grid-template-columns: 12% 10% 78%
grid-template-rows: 38% 2% 60%
grid-template-areas: |
  "graph header header"
  "info_top section_select_top main_top"
  "info_buttons section_select control_area"
```

In the example above, we've defined a nine-square, 3x3 grid, like tic-tac-toe. _Unlike_ tic-tac-toe, however, we've squished some of the lines together by using percentages. My understanding is that in CSS, percents are always in relation to the enclosing container. (I might be wrong about that, I welcome feedback.) Anyway, this makes, roughly, this grid:

![grid](https://github.com/user-attachments/assets/e110a1c7-10f8-4506-9d26-e4fdcdccccbf)

Then, under grid-template-areas, we give all those areas names. Areas can have multiple names, and areas can span more than one grid space, like _header_ does. Hopefully you can see where we're going with this. Have a look here:

<a href="https://www.thelcars.com/themes/nemesis-blue.html">TheLCARS.com LCARS layout</a>

If your screen isn't wide enough, you won't see the left-hand "sidebar" with the little animated doodad.

Anyway, the cards on the template are laid out to be in these sections, and you can see this in the code of the various cards, which looks like this:

```
view_layout:
  grid-area: info_top
```

This snippet tells the element where in the grid to go. The element can span more than one cell, this is done like this:

```
 grid-row-end: span 1
```

You can also specify column-row-end, and you don't have to specify a "span _n_", you can use the name of the ending row or column.

There's a _lot_ you can do with CSS grid layouts, see more information on the lovelace-layout-card page, and this page here:

<a href="https://css-tricks.com/snippets/css/complete-guide-grid/">CSS Grid Layout Guide</a>

Anyway, each layout I'll post here will need its grid adjusted in the view css to look correct. You'll _also_ probably need to play with the following code in the header vertical stack:

```
--lcars-vertical-border: 3.45em !important;
--lcars-horizontal-border: 0.2em !important;
```

You'll want to adjust those numbers so that they line up nicely with the buttons, and size nicely for your device.
