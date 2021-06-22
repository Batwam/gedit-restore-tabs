## gedit Restore Tabs

This is a plugin for [gedit][1], the official text editor of the GNOME desktop
environment. It's a fork from the no more maintained [restore-tabs plugin](https://github.com/Quixotix/gedit-restore-tabs), originally written by Micah Carrick, without a license attached to it.

It contains fixes to work with Python 3, fixes to Gnome 3.38, fixes collected from [Kasual branch](https://github.com/Kasual/gedit-restore-tabs) and [Hildo Guillardi Júnior branch](https://github.com/hildogjr/gedit-restore-tabs) and an additional fix to restore files with blank space paths.

This plugin is for gedit versions 3.36 and above (included in Ubuntu 20.04).

**This plugin is NOT compatible with gedit 2.x**.

Upon starting gedit, this plugin will try to restore all open documents from the  *last* gedit window that was closed.

Installation
------------

1. Download the source code from this repository, and extract the contents: 

       wget https://github.com/raelgc/gedit-restore-tabs/archive/master.zip -O gedit-restore-tabs.zip
       unzip gedit-restore-tabs.zip

2. After extraction, copy all the files that begin with `restoretabs.*` to your local `gedit` plugins directory, located at `~/.local/share/gedit/plugins/`:

       cd gedit-restore-tabs-master
       mkdir -p ~/.local/share/gedit/plugins
       cp restoretabs.* ~/.local/share/gedit/plugins/   
     
3. Copy and compile the settings schema as **sudo/root**. We need to add a `glib` schema, and gedit looks for such schema in the `/usr/` directory in the file system. Thus, we will need to root privileges, in order to put the newly compiled schemas database in that location.

       sudo cp org.gnome.gedit.plugins.restoretabs.gschema.xml /usr/share/glib-2.0/schemas/
       sudo glib-compile-schemas /usr/share/glib-2.0/schemas/

4. Restart gedit, and activate the plugin by going to `Edit` > `Preferences`, selecting the `Plugins` tab and marking the checkbox by the `Restore Tabs` entry.

[1]: http://www.gedit.org
