<!-- ![stability-experimental](https://img.shields.io/badge/stability-experimental-orange.svg?style=for-the-badge) -->
![GitHub issues](https://img.shields.io/github/issues-raw/jeblad/LuaLexer?style=for-the-badge)

 ***NOTE***: *This is only in the preparation. The goal is to insert [LoganDark/lua-lexer](https://github.com/LoganDark/lua-lexer) and make it avaiulable.*

This [extension for Mediawiki](https://www.mediawiki.org/wiki/Extension:ModDoc) add a Lus lexer for modules provided by the [Scribunto extension](https://www.mediawiki.org/wiki/Extension:Scribunto). This makes it possible to build a parse tree for Lua code, to facilitate further analyzis in a collaborative environment.

## Usage

LuaLexer depends on the Scribunto extension, and provide a parse tree for Lua code.

1. Download from [Github](https://github.com/jeblad/LuaLexer) ([zip](https://github.com/jeblad/LuaLexer/archive/master.zip)) and place the file(s) in a directory called LuaLexer in your extensions/ folder.
2. Add the following code at the bottom of your LocalSettings.php:

	```lua
	wfLoadExtension( 'LuaLexer' );
	```

3. Done – Navigate to Special:Version on your wiki to verify that the extension is successfully installed.

## Development

LuaLexer uses [Mediawiki-Vagrant](https://www.mediawiki.org/wiki/MediaWiki-Vagrant), and an instance can be made quite easily. A more complete setup can be found at the page [vagrant](../../wiki/vagrant).

1. Make sure you have Vagrant, etc, prepare a development directory, and move to that directory.
2. Clone Mediawiki

	```bash
	git clone --recursive https://gerrit.wikimedia.org/r/mediawiki/vagrant .
	```

3. Add the role unless [#?](https://gerrit.wikimedia.org/r/#/c/mediawiki/vagrant/+/?/) has been merged. (You need [git-review](https://www.mediawiki.org/wiki/Gerrit/git-review) to do this.)

	```bash
	git review -d ?
	```

4. Run setup.

	```bash
	./setup.sh
	```

5. Enable role for LuaLexer. This pulls in the role for Scribunto, which then pulls in additional roles.

	```bash
	vagrant roles enable lualexer
	```

6. Start the instance.

	```bash
	vagrant up
	```

7. Done.
