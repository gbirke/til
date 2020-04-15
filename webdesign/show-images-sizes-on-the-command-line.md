# Show image sizes on the command line
The `identify` command from ImageMagick can show all kinds of information. By default, it shows all information. If you want to select specific information, you need to pass a [`format` parameter](http://www.graphicsmagick.org/GraphicsMagick.html#details-format):

	identify -format "%f %wx%h\n" *.png

Thanks to https://superuser.com/questions/275502/how-to-get-information-about-an-image-picture-from-the-linux-command-line
