# ha-lcars-layout-templates
Some templates for HA-LCARS

Here are some grid layouts for your Home Assistant HA-LCARS needs.

In messing around with Home Assistant, I ran across the delightful HA-LCARS theme. Now, the two people who know anything about me know that I'm 1) a giant Star Trek nerd with an encyclopedic knowledge of most of the franchise from TNG onward and 2) a general home automation nerd. Naturally, I was drawn to the intersection of a real and imagined future with Home Assistant and theming it to look like Michael and Denise Okuda's amazing work designing the user interface of the fuuuutreeeee in Star Trek: TNG. It's a very recognizable interface, and I - along with lots of others - think the general use of color and shapes seems very usable. Anyhoo. In setting about to recreate some of the layouts we see on-screen, I ended up deciding to use lovelace-layout-card grids, which lets you define CSS grids and position things with them. This seems, by *far*, the best way to position things within the HA system. I decided maybe the community could use my snippets, and so, here they are.

To use, install all the dependencies, and then copy / paste from the file you want to use into the yaml editor of your layout.

You WILL have to adjust sizing to make everything align. Right now, most of the elements are not particularly scalable - or they might be, and I'm doing it wrong, I welcome correction on that - but coding something totally self-resizing is beyond my capabilities. So you'll likely need to adjust for your device. The way I get around this is to copy these views and then resize them for a specific device. Since I only have one or two displays in my house for interacting with HA, that's fine for me.
