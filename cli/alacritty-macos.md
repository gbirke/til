# Configure Powerline Fonts in Alacritty for macOS

I'm using the font "Meslo LG S DZ for Powerline" from the [powerline fonts
repository](https://github.com/powerline/fonts) and was trying to use it with
the terminal program [Alacritty](https://github.com/alacritty/alacritty). It did not work
out of the box, I had to do the following steps:

1. Create the file `~/.config/alacritty/alacritty.yml`, copying the contents of [the
   example
   file](https://raw.githubusercontent.com/alacritty/alacritty/master/alacritty.yml).
2. Uncomment the `fonts:` section (it's is own section with no identation). For the
   `familiy`, put in `Meslo LG S DZ for Powerline` without quotes or other specifiers
   (Regular, etc), put those in the `style` key.
3. Uncomment the `env:` section and add the following key:  
     `LC_CTYPE: UTF-8 `  
   Without this key, Alacritty won't display the Powerline characters.
