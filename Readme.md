# Lingo

 Lingo is a linguistics module, currently providing inflection and some string transformations. Eventually I would like to extend its capabilities and add additional languages.

## Installation

    $ npm install lingo

## Inflection

Lingo provides English inflection rules by default, which of course can be extended. View _./lib/languages/en.js_ for more information.

### Language#pluralize()

Convert a singular word to it's plural alternative:

    en.pluralize('fox');
    // => "foxes"

### Language#singularize()

Convert a plural word to it's singular alternative:

    en.singularize('foxes');
    // => "fox"

### Language#isPlural()

Check if a word is plural:

    en.isPlural('foxes');
    // => true

    en.isPlural('fox');
    // => false

### Language#isSingular()

Check if a word is singular:

    en.isSingular('fox');
    // => true
    
    en.isSingular('foxes');
    // => false

## Transformations

### lingo.capitalize()

Capitalize the first word of a string:

    lingo.capitalize('hello there');
    // => "Hello there"

Capitalize all words:
 
    lingo.capitalize('hello there', true);
    // => "Hello There"

### lingo.camelcase()

Camelcase a string:

    lingo.camelcase('foo bar');
    // => "fooBar"

Camelcase with first character upppercase:

    lingo.camelcase('foo bar baz', true);
    // => "FooBarBaz"

## lingo.join()

Defaults to "and":

    lingo.join(['fruits', 'veggies', 'sugar']);
    // => "fruits, veggies and sugar"

Supplying "or":

    lingo.join(['fruits', 'veggies', 'sugar'], 'or');
    // => "fruits, veggies or sugar"

## i18n (translations)

New languages can be defined as shown below:

    var Language = require('lingo').Language
      , fr = new Language('fr');

    fr.translations = {
      'Welcome {name}': 'Bonjour {name}'
    };

The language code passed to `Language()` self-registers itself, so you could grab the implementation via:

    var fr = require('lingo').fr;









































































