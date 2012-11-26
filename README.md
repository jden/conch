# conch
format markdown for console output

## Installation

    $ npm install conch

## Usage

    var conch = require('conch');
    var fs = require('fs');

    fs.readFile(__dirname + '/README.md', function (err, file) {
      if (err) return console.error(err);
      console.log(
        conch(file.toString())
      );
    });

Note, conch is implemented as a formatter using the fantastic [marked](http://npm.im/marked) markdown parser. It works by parsing tokens generated by `marked.lexer()`. Ordinarily, calling `conch()` on some markdown will call that for you. But if you happen to have an array of `marked` tokens laying around, you can pass that directly to `conch.parse()`. Let the md AST mangling commence!

## License
MIT. (c) 2012 jden - Jason Denizac <jason@denizac.org>