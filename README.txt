Auth Redux Lite Mod v2.7
By Leslie Krause

Auth Redux Lite is available for server operators that want a barebones, no-frills 
authentication handler for their server. The entire mod consists of a single 13 kB file.

This fork uses the same database API and architecture as Auth Redux, so migration is 
completely seamless. If you are already using Auth Redux, simply backup your existing 
"auth_rx"' subdirectory, and then save the included "init.lua" file in its place.

However, if you are migrating from the builtin auth handler of Minetest 5.x, then there 
are a few additional steps depending on the specific database backend you are using.

  Convert auth.txt
  ---------------------
  1) Create an "auth_rx_lite" subdirectory under mods in your game.
  2) Run the included Database Import Script to convert the database.
     
     awk -f convert.awk -v mode=install ~/.minetest/worlds/world/auth.txt

  Convert auth.sqlite
  ----------------------
  1) Create an "auth_rx_lite" subdirectory under mods in your game.
  2) Run the Minetest server to migrate the SQLite3 auth database backend.

     minetestserver --migrate-auth files --worldname world

  3) Run the included Database Import Script to convert the database.
     
     awk -f convert.awk -v mode=install ~/.minetest/worlds/world/auth.txt

In the examples above, you will need to provide your world directory. I'd also recommend 
moving or simply renaming the auth.txt file to "auth.txt.bak" for safekeeping.

That's all there is to it!


Compatability
----------------------

Minetest 5.3+ required

Repository
----------------------

Browse source code:
  https://bitbucket.org/sorcerykid/auth_rx_lite

Download archive:
  https://bitbucket.org/sorcerykid/auth_rx_lite/get/master.zip
  https://bitbucket.org/sorcerykid/auth_rx_lite/get/master.tar.gz

Source Code License
----------------------

The MIT License (MIT)

Copyright (c) 2016-2020, Leslie Krause (leslie@searstower.org)

Permission is hereby granted, free of charge, to any person obtaining a copy of this
software and associated documentation files (the "Software"), to deal in the Software
without restriction, including without limitation the rights to use, copy, modify, merge,
publish, distribute, sublicense, and/or sell copies of the Software, and to permit
persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or
substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED,
INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR
PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE
FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR
OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
DEALINGS IN THE SOFTWARE.

For more details:
https://opensource.org/licenses/MIT
