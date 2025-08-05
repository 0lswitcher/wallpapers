<p align="center">
  <img src="https://raw.githubusercontent.com/0lswitcher/dotfiles/refs/heads/main/md-assets/fastfetch/oracle-ff-logo-none.png" style="width: 203px; height: 262px">
</p>

<h1 align="center">
  fastfetch configuration/dot files
</h2>

Yo, welcome to my fastfetch configuration files. Below I've included screenshots of the different ways you can configure fastfetch with my dotfiles, along with some details of what specifically to change to get the same results, and some useful tips I learned along the way.

>  [!NOTE]
>  I highly recommend checking out the [official documentation/wiki](https://github.com/fastfetch-cli/fastfetch/wiki/Configuration) when delving deeper into fastfetch configuration as it's super nice to have when trying to determing formatting related things.

>  [!NOTE]
>  In the screenshots, Im using Hyprland with transparency effects enabled, and base16-harmonic terminal colors-so keep that in mind when attempting to recreate the look. 

---

First, here's a screenshot of only the modules in my fastfetch configuration so I can give you \
a run down of the important things before we go into logo's.

<p align="center">
  <img src="https://raw.githubusercontent.com/0lswitcher/dotfiles/refs/heads/main/md-assets/fastfetch/oracle-ff-logo-none.png" style="width: 305px; height: 394px">
</p>

A few things to note before we proceed. Besides the obvious non-default icons and things of \
the like, some things such as the CPU details are custom to avoid bloat. \
For an example of what I'm referring to, here's a screenshot with the default cpu configuration:

<details>
  <summary>(Click me to see)</summary>
  <p align="center">
    <img src="https://raw.githubusercontent.com/0lswitcher/dotfiles/refs/heads/main/md-assets/fastfetch/fastfetch-overflow.png" style="width: 305px; height: 394px">
  </p>
</details>

See how the cpu details overflow the custom bracket design? To fix this, I referenced the \
[official documentation](https://github.com/fastfetch-cli/fastfetch/wiki/Configuration), opened 
the config.jsonc and changed:

```
        {
            "type": "custom",
            "key": "  ├ ",
            "keyColor": "green"
        },
```

to

```
        { // custom formatting since the automatic one is bloated
            "type": "cpu",
            "key": "  ├ ",
            "keyColor": "green",
            "format": "Intel Core i9-9900k (16) @ {freq-max}"
        },
```

This gave me the desired results. 

You'll also notice the crosses displaying my terminal colors. This can easily be changed to any \
glyph or symbol desired as long as your configured fonts support it. Make sure to peek in the \
config.jsonc, since I have a ton of other templates commented out and ready to be swapped in \
at a moments notice. Things like pacman and ghosts, stars, gradient circles, and more.

---

Now it's time for **logos**

> [!IMPORTANT]
> Make sure you're adding commas (`,`) after each line of code that has another proceeding. 

First, here's how it look's with `"type:"` set to `"auto"` on my setup:

<p align="center">
  <img src="https://raw.githubusercontent.com/0lswitcher/dotfiles/refs/heads/main/md-assets/fastfetch/oracle-ff-logo-auto.png" style="width: 618px; height: 442px">
</p>

Next, here's how it looks with `"type":` being commented out, `"source":` being set to \
`~/.config/fastfetch/terminal_art.txt"`:

<p align="center">
  <img src="https://raw.githubusercontent.com/0lswitcher/dotfiles/refs/heads/main/md-assets/fastfetch/oracle-ff-logo-custom.png" style="width: 766px; height: 442px">
</p>

If you're attempting to recreate the look in the first screenshots where only the modules are \
visible, make sure you have the _terminal_art_blank.txt_ downloaded and placed in your \
fastfetch configuration location, then recreate the above step-replacing `terminal_art.txt` \
with `terminal_art_blank.txt`.

That's about it though! Only thing from here for you to do is mess with colors, experiment by adding your own ascii art to the `terminal_art.txt` file, and anything else you can think of to make it \
your own. Thanks for reading, and have fun configuring!
