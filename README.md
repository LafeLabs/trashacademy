# Bioweb

## [localhost/](http://localhost/)

## [www.trashrobot.org](https://www.trashrobot.org)

## [GITHUB.COM/LAFELABS/BIOWEB](https://github.com/LafeLabs/bioweb)

## [Geometron THING git repository](https://github.com/lafelabs/thing/)

#  <span style = "color:red">B</span><span style = "color:orange">I</span><span style = "color:yellow">O</span><span style = "color:green">W</span><span style = "color:blue">E</span><span style = "color:purple">B</span>


 - everything replicates(all code can be replicated by all users at all times)
 - everything evolves(all code can be edited by all users at all times)
 - everything dies(all code can be deleted by all users at all times)

[readme.html](readme.html)

[home](index.html)

The raw global replicator code for this is found here:

[https://raw.githubusercontent.com/LafeLabs/bioweb/master/php/replicator.txt](https://raw.githubusercontent.com/LafeLabs/bioweb/master/php/replicator.txt)

[local replicator link](php/replicator.txt)

Edit code using editor.php:

[editor.php](editor.php)

Replicate Geometron sets with set.html:

[set.html](set.html)

To replicate this set, create a new repository, get PHP working from the command line on your machine(mac, pc, linux all work), then copy the file [php/replicator.txt](php/replicator.txt) into a new file called replicator.php, and run it.  Once you've run it, be sure permissions are ok, and run 

<pre>
php -S localhost:80
</pre>

from the command line, then point a browser on your machine to "localhost://".  Then click on the [editor](editor.php) to edit the code.  Use the editor to change the value of the code in php/replicator.txt to point to the dna.txt and replicator.txt raw text files of your new repository, then run the program [text2php.php](text2php.php) to convert the text you edited to a live php script.  To add files, instead of pointing your browser to editor.php, point it to editor.php?newfile=[name of new file].  When you've added any files, run [dnagenerator.php](dnagenerator.php) to add them to your dna.  Then update the global copy of your repository on Github, and you should be able to copy your newly modified replicator code into the root web directory *anywhere* that has a running web server, run it from any browser, and your web app will replicate.  

That new instance can then be modified in the same way, the code updated in the replicator to point to the new global instance as it evolves.  Any given app can replicate an arbitrary number of times as is, or can mutate instantly and be abandoned.  It's up to you. 

Web servers on which this have been tested include paid hosts dreamhost and bluehost, free hosting at 000webhost, php localhosts on windows, mac and linux, Apache run on a Raspberry Pi and on an Ubuntu virtual machine, on windows and linux machines with [XAMPP](https://www.apachefriends.org/index.html), on the Android using [KSWEB](https://www.kslabs.ru/), on iOS using [phpwin](https://app.phpwin.org/).  You need write permission and PHP running and you're good to go.  

To install Apache, PHP and Geometron from the command line on Raspberry Pi, 

enter:

<pre>
sudo apt update
sudo apt install apache2 -y
sudo apt install php libapache2-mod-php -y
</pre>

then

<pre style = "overflow:scroll">
cd /var/www/html
sudo rm index.html
sudo curl -o replicator.php https://raw.githubusercontent.com/LafeLabs/bioweb/master/php/replicator.txt
cd ..
sudo chmod -R 0777 *
cd html
php replicator.php
sudo chmod -R 0777 *
</pre>

### Use cases

 - [geometron](https://www.trashrobot.org/)
 - shopping center pages
 - corner market
 - rideshare
 - mutual aid coordination 
 - personals ads
 - local news feeds
 - dumpster updates for scavengers
 - self-replicating open source hardware replicators
 - self-replicating custom calculators for specific technical applications
 - building general self-replicating HTML applications to do any arbitrary task
 - personal home pages
 - local bulletin boards in a community space served over the wifi
 - self-replicating zines


## Structural Elements of the System:

Languages: PHP, HTML, JavaScript, CSS, Markdown, JSON

THERE ARE NO DATABASES

 - [replicator.php](php/replicator.txt): replicates the system using the file [data/dna.txt](data/dna.txt)
 - [fileloader.php](php/fileloader.txt): loads and prints files from the server filesystem 
 - [filesaver.php](php/filesaver.txt): saves files to the server filesystem
 - [editor.php](php/editor.txt): a general code editor which can edit all parts of the system, and formats code using the [Ace.js library](https://ace.c9.io/)
 - [text2php.php](php/text2php.txt): a script which copies every file in the php directory(all of which use the .txt extension so browsers can read them) into the main directory with the .php extension so that they can run.  This prevents editor.php from breaking things in real time while they are edited.
 - [dnagenerator.php](php/dnagenerator.txt): this script reads from the server file system to see what files exist and put them in the file [data/dna.txt](data/dna.txt) so that the replicator can find them all using the dna
 - [setreplicator.php](php/setreplicator.txt): copies a set of files described by the JSON file [data/set.txt](data/set.txt)
 - [removephp.php](php/removephp.txt): removes all .php scripts, making the page passive.  This will break fileloader.php which breaks index.html, so it can also be used with the "keeploader" flag with fileloader.php?keeploader to keep the loader and delete all other .php scripts to avoid a page getting edited if it faces the wider Internet and you don't want it "hacked"
 - [setreplicator.php](php/setreplicator.txt): a script which copies all the files listed in [data/set.txt](data/set.txt)
 - [README.md](README.md): this document. By default index.html and readme.html both read this, and it is also by default the document seen on the github repository
 - [readme.html](readme.html): a page which reads the README and converts it to html for easy viewing in a browser
 - [index.html](index.html): home page, where browsers start pointing to.  Edit to anything using editor.php.  There are no limits to what this can do.
 - [scrolleditor.html](scrolleditor.html): the editor for markdown files, in this case just README.md but if you replicate a more full version of Geometron it can edit an arbitrary number of markdown files, and it is easily edited using editor.php to edit other types of file of all kinds
 - [set.html](set.html):  The operation page for the self-replicating set of files found in [data/set.txt](data/set.txt) which points to source and destination locations
 - [data/dna.txt](data/dna.txt): a JSON file which lists all the files replicated by replicator.php
 - [data/set.txt](data/set.txt): a JSON file which lists files to replicate using setreplicator.php



