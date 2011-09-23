mcweather - Minecraft-Weather addon for Minecraft-Overviewer
=============

![mcweather](http://i.imgur.com/z1KMh.png)

This will generate 2 icons on your Overviewer map. The first is your current conditions, the second is what the next change will likely be, and a small text under both explaining when and what will happen in the forecast.

Requirements
-------

* [Overviewer 0.1.3+](https://github.com/overviewer/Minecraft-Overviewer) -- Map generation in the format of google maps, can be most forks of this project, but brownan's is typically the main project I support
* [PHP 5.2+](http://php.net/) -- Your host/server must be able to parse the php language in order to support this script. More importantly you'll need php 5.2 or higher due to the use of the json functionality that was introduced in php5.2.
* [nbt.class.php](http://svn.thefrozenfire.com/minecraft/NBT/trunk/) -- I've coded this script to use FrozenFire's nbt class. This can be placed in the same directory as your php 'include_path' on your host.

Installation
-------

1.) Edit the `getServerWeather.php` in a text editor:
    
    $nbt->loadFile("<serverDIR>/level.dat");
    
2.) Edit the `mcweather.js` in a text editor:
    
    var forecastAccuracy = 25000; // number of ticks to predict within. 20 ticks a second.
    var workingDIR = '/mcweather';  // default should work, unless you have something like example.com/~user/map/mcweather. NO TRAILING SLASH!
    
3.) Reference the mcweather.js in Overviewer by locating in your index.html (Default location for this is in the `web_assets` folder in your Overviewer directory). This line will be inserted anywhere before the `</head>` of your index file:

    <script type="text/javascript" src="mcweather/mcweather.js"></script>

4.) Save all 3 files and copy all contents of the folder to your overviewer output folder or the `web_assets` folder of Overviewer.
    
Todo
-------

- better forecasting based on actual percents from the server.
- detect day night in forecast.

Thanks
-------

- aheadley has provided huge support in deciphering the values stored in the level.dat nbt file.
- Paul Davey for providing the use of his Buuf icons. http://mattahan.deviantart.com/art/Buuf-37966044
- Frozenfire for developing easily the most popular nbt library for manipulating the data in the Minecraft nbt files.

Support
-------

Any inquires can be opened in the issues tab above, or join us on irc.freenode.net in [#overviewer](http://webchat.freenode.net?channels=overviewer)!
