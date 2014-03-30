InfiniteSky
=========

InfiniteSky is an open-source project, emulating a Twelve Sky Server. It is written in Node.JS

  - Currently the world server part is being re-intergrated into the code base
  - So you cant login to world just yet but I am working on it :).
  - Code will under go cleaning and documentation.

Version
----

1.0.00 - Tomato Soup

Tech
-----------

InfiniteSky uses a number of open source projects to work properly:

* [hexy] - hexdump, binary pretty-printing
* [async] - Higher-order functions and common patterns for asynchronous code
* [xtend] - extend like a boss
* [jshint] - Static analysis tool for JavaScript
* [socket] - Socket is a connect clone for simple socket based applications
* [netmask] - Parse and lookup IP network blocks
* [node.js] - evented I/O for the backend
* [mongodb] - A NoSQL DB that is awesome
* [mongoose] - Mongoose MongoDB ODM
* [vmscript] - Scripts that reload when changed and run in a node vm [@LiamKarlMitchell]
* [socket.io] - a super fast port of Markdown to JavaScript apps
* [restruct.js] A JavaScript binary data library. [@rfw]

If you need a runtime debuger, I would suggest node-inspector
Example usage: npm install node-inspector -g
node-debug main

Installation
--------------

##### Install Node.js & MongoDB
*If you have not already*
Currently using Node.js v0.10.26

Don't use the one from apt-get on linux, I have had experiences with it being majorly out of date.

See the following links:
* http://nodejs.org
* http://www.mongodb.org

Server is currently untested on linux. I have been running it on Windows 7
```sh
git clone [git-repo-url] InfiniteSky
cd InfiniteSky
npm install
mkdir data
mkdir data/infos
mkdir data/packets
mkdir data/spawninfo
mkdir data/world
```

##### Copy game files to data directorys you made

for more information on these directorys look at *docs/directorys.md*

data/infos:
* G03_GDATA/D01_GIMAGE2D/005/*.IMG

data/world:
* G03_GDATA/D07_GWORLD/*.WM
* G03_GDATA/D07_GWORLD/*.WREGION
* 
##### Configure. Instructions in 
cp config.json-dist config.json
and edit it accordingly

* docs/config.md

Replace the following in the config
"PUT YOUR INTERNAL IP HERE" with your ip address you can find it by doing ipconfig and looking at your interfaces ip.
"PUT YOUR NETWORK MASK HERE" Your nemask in cider notation. For example "10.1.1.0/24" is 255.255.255.0
"PUT YOUR EXTERNAL IP HERE" Get your external ip by googling what is my ip and putting the result in here. This is required for other people to connect to your server. Otherwise use your internal IP if running on lan.

##### Configure Plugins. Instructions in following README.md files

* plugins/dropbox/README.md
* plugins/github/README.md
* plugins/googledrive/README.md

```sh
node app
```

##### Scripting Documentation

* docs/scripting.md

##### Game Launcher and TSX Client DLL

Compile the launcher and dll and package them together.
The PrivateServer.ini should look like this
```ini
[PrivateServer]
BypassGameGuard = 1
MultiClient = 1
ChangeIP = 1
ServerIP = 127.0.0.1
HookFileLoading = 1
DevButtons = 1
```

##### Notes

The server will take a while to start, be patient.


License
----

GNU GPL see LICENSE file

**Enjoy!**
    