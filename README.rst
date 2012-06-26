
jtmpl
================================================================================

jtmpl is a commandline app for quickly running jsontemplate. This lets you generate templated files without having to code, making jsontemplate more useful for build processes, system administration, and static HTML page generation.

jtmpl happens to be implemented in python, but you don't need to be using python in your project to take advantage of it.


For more about JSON Template, see:

http://json-template.googlecode.com



An Example
================================================================================

jtmpl is useful for when you have some type of form you want filled out with a data file that you already have. The data should be in JSON or easily convertable to JSON.

The example included with json-template is a long story about a music app, but let's make a quick address book and a letter we want to send to all the people in the address book::

	{.repeated section names}
	
	Dear {@},
	
	I think you are really awesome.
	
	Sincerely,
	{my_name}
	
	--------------------------- CUT HERE --------------------------------
	
	{.end}

That was the "template file". Here's the JSON data::

	{
		"my_name": "Poppy",
		"names": [
			"Meghan",
			"Andy",
			"Josh",
			"Eden",
			"Andy",
			"Mateusz"
		]
	}

Put the template into letter.jtmpl.txt and the json data into names.json and run it like this::

	$ jtmpl names.json letter.jtmpl.txt

you will get::

	Dear Meghan,
	
	I think you are really awesome.
	
	Sincerely,
	Poppy
	
	--------------------------- CUT HERE --------------------------------
	
	
	Dear Andy,
	
	I think you are really awesome.
	
	Sincerely,
	Poppy
	
	--------------------------- CUT HERE --------------------------------
	
	
	Dear Josh,
	
	I think you are really awesome.
	
	Sincerely,
	Poppy
	
	--------------------------- CUT HERE --------------------------------
	
	
	Dear Andy,
	
	I think you are really awesome.
	
	Sincerely,
	Poppy
	
	--------------------------- CUT HERE --------------------------------
	
	
	Dear Eden,
	
	I think you are really awesome.
	
	Sincerely,
	Poppy
	
	--------------------------- CUT HERE --------------------------------
	
	
	Dear Mateusz,
	
	I think you are really awesome.
	
	Sincerely,
	Poppy
	
	--------------------------- CUT HERE --------------------------------


See the JSON Template documentation if you want to do anything more complicated.

http://json-template.googlecode.com



Installing
================================================================================



Installation via cheeseshop / easy_install / pip
--------------------------------------------------------------------------------

Typical python method.

GOOD
	* pretty easy!
	* compatable with virtualenv
BAD
	* changes your python / system environment
	* usually requires root, unless using virtualenv

run::

	pip install jtmpl

or::

	easy_install jtmpl


That's it!



Installation manually
--------------------------------------------------------------------------------

More customizable installation method.

GOOD
	* works in all sorts of situations installers might not consider
	* does not require root

BAD
	* most likely to require troubleshooting - please try other install methods first!

do::

	cd jtmpl
	curl 'https://json-template.googlecode.com/files/json-template-0.85.zip' > json-template-0.85.zip
	unzip json-template-0.85.zip
	ln -s `pwd`/jtmpl.sh ~/local/bin/

taking care to have the folder where you would like it (ie, ~/local/share/jtmpl/ ) and the resultant symlink as well (ie, ~/local/bin/jtmpl )



Installation otherwise?
--------------------------------------------------------------------------------

Have another way you would like to install apps? Let me know!



License
================================================================================

PERFECT USE OF JTMPL!

see: http://www.opensource.org/licenses/BSD-2-Clause

data::

	{
		"OWNER": "Paul Oppenheim",
		"YEAR": 2012
	}

template:

Copyright (c) {YEAR}, {OWNER}
All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

	* Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

	* Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

