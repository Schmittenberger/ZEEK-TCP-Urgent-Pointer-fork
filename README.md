<h1 align="center">
 Zeek fork with TCP Urgent Pointer and IP Reserved Bit

</h1><h4 align="center">

A ***complicated*** framework for network traffic analysis and security monitoring.

[_Key Features_](#key-features) —
[_Getting Started_](#getting-started) —
[_Development_](#development) —
[_License_](#license)

</h4>


Why this fork? 
--------------
* This Zeek fork adds the TCP Urgent Pointer to the header, as well as the Reserved Bit field to the IPv4 header. A zeek plugin could add the same functionality, but as no proper documentation (with relevant examples! Don't tell me to 'just read the source code' - source code is not documentation!) on writing plugins exists, and after existing third party plugins not compiling on their latest state, it was counterintuitivly faster to modify the source code.

* I use this fork together with my Zeek scripts to detect covert channels on IPv4 and TCP protocols. See [Zeek-CCgen](https://github.com/Schmittenberger/Zeek-CCgen.v2).

Getting Started
---------------

The place to find information about getting started with Zeek is [www.zeek.org](https://www.zeek.org), specifically the sparse
[documentation](https://www.zeek.org/documentation/index.html) section. On the web site you can also find tutorials on getting Zeek set up. Unfortunatly, not a lot of code examples or well written documentation is available for Zeek. 

Clone the master git repository:

`git clone --recursive https://github.com/Schmittenberger/ZEEK-TCP-Urgent-Pointer-fork`

Install all [dependencies](https://docs.zeek.org/en/stable/install/install.html#prerequisites) locally.
Then configure build with:

`./configure`

(Optionallly enable ccache (sudo apt install ccache) to speed up recompile, if you are further developing this fork. Optionally enable debug to be able to debug plugins and optionally set a custom install path for the fork:) `./configure --ccache --enable-debug --install-dir=...`

Next build and install:

`make && sudo make install`

(this may take a while the first time)

Development
-----------
This Zeek fork wont receive any updates after my thesis. Feel free though to take my changes and incorporate them in your own build.


License
-------

Zeek comes with a BSD license, allowing for free use with virtually no
restrictions. You can find it [here](https://github.com/zeek/zeek/blob/master/COPYING).
