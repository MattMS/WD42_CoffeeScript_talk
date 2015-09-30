# CoffeeScript

Still worth a look



## Me?

- Matt McKellar-Spence

- GitHub: [MattMS](https://github.com/MattMS/)

- Twitter: [MattMS](https://twitter.com/MattMS)



## Such magic?

- [reveal.js](https://github.com/hakimel/reveal.js)

- [Jade](http://jade-lang.com/)

- [Stylus](https://learnboost.github.io/stylus/)



...and a little [CoffeeScript](http://coffeescript.org/) :)



## First

- ES(6|7|201[56]) look (mostly) good.

- I like CoffeeScript syntax, you may not.

- Same idea as Sass, Less, Jade, etc.


## Hard and fast

But totally worth learning.

- Vim

- Regular expressions



## And now for something completely different...



## Python!

[python.org](https://www.python.org/)

First step to liking CoffeeScript.



## Pretty basic

```python
hopefully_a_name = input('Who be ye? ')

print('Yo', hopefully_a_name)
```



### Fully functional

```python
def but_is_it_awesome(questionable_item):
	if questionable_item in ['CoffeeScript', 'Python']:
		return 'yeah'

	elif questionable_item != 'Java':
		return 'maybe'

	else:
		return 'nah'

print(but_is_it_awesome('Lua'))
```


### Stay classy

```python
class MeatSack:

	def __init__(self, name):
		self.name = name

	def talk(self):
		return 'Me {}'.format(self.name)

meaty = MeatSack('T-Bag')

print(meaty.talk())
```


### Reusing concepts

```python
10 in [2, 6, 12, 16, 60]

'nah' in 'banana'

'base' in {'base': 0xc, 'value': 'a'}
```



## Why Python?

- Syntax is well-considered.

- You were going to indent it anyway, right?



## What about YAML!

[yaml.org](http://yaml.org/)

(nearly coffee-time)



## Orderly but approachable

```yaml
- date: 2015-09-30
  place: Typewriter Factory
  task: Talk about CoffeeScript.

- date: 2015-10-01
  place: Antarctic Division
  task: Last day shenanigans.

- date: 2015-10-02
  place: The Winston
  task: Eat ribs and drink beer.
```



## Why YAML?

- Safe for our puny human brains.

- Only write what you need.


### ...but

- Better for configuration than transport.

- Use `safe_load`.



## CoffeeScript!

Yay?



## Must know JavaScript

- CoffeeScript is JavaScript.

- Most documentation/libraries are in JavaScript.

- You will probably debug the JavaScript with browser tools.



## A simple function

```coffee
greet = (name)->
	'Hello ' + name
```

Free returns!



## Do you really like brackets?

```javascript
console.log(greet('World'))
```

or

```coffee
console.log greet 'World'
```

(Sorry Lisp folk)


Think of the command line.

`git add main.coffee`


Well, think in reverse (if you must).

`'World' > greet > console.log`



### Yes, long lines are confusing

```coffee
wha = do_something with_this + this_too and_me / wait_what
```

which is apparently

```javascript
wha = do_something(with_this + this_too(and_me / wait_what))
```

So instead...



### Moar lines!

```coffee
chance_of_distracting_shopkeep = attractiveness * magic_skillz

shopkeep_attention = 1 / shopkeep_hours_on_shift

pizza_slices_acquired =
	if chance_of_distracting_shopkeep > shopkeep_attention
		all_the_slices
	else
		money_in_pocket / cost_of_pizza_slice
```



## Keep it simple

- Everything is an expression (returns something).

- One liners are fun to write, but to read?



## Functions and arguments

```coffee
path = require 'path'

parts = path.parse path.join site, folder, file
```

gives

```javascript
var path = require('path')

var parts = path.parse(path.join(site, folder, file))
```


Alternatively

```coffee
path = require 'path'

parts = path.parse path.join [
	site
	folder
	file
]...
```



## Literate CoffeeScript

I love this stuff.



### Have you ever

- Separated your code with fancy comment lines?

- Run out of space with indented comments?

- Made up your own comment styles?



### Describe, then code

```coffee
# My cool server

	http = require 'http'

	server = http.createServer (req, res)->
		res.writeHead 200, 'Content-Type': 'application/json'
		res.end JSON.stringify ok: true

## Start server

Start the server on [port 1337](http://localhost:1337).

	server.listen 1337
```



### It's just Markdown

- Break up sections with headings.

- All comments get the same width.

- Looks cool on GitHub.

- [Readme Driven Development](https://tom.preston-werner.com/2010/08/23/readme-driven-development.html)



## The big stuff



### Big comments

```coffee
###
So much space to fill with (almost) whatever you like.

Literate CoffeeScript is nicer though.

You only get 2 Markdown heading levels with this.
###
```



### Big strings

```coffee
reaction = 'Woah!'

all_the_stuff = """
#{reaction}

I <em>strongly</em> dislike
<abbr title="Hypertext Markup Language">HTML</abbr>,
but how awesome is this!
"""
```



### Big regexes

```coffee
OPERATOR = /// ^ (
?: [-=]>            # function
| [-+*/%<>&|^!?=]=  # compound assign / compare
| >>>=?             # zero-fill right shift
| ([-+:])\1         # doubles
| ([&|<>])\2=?      # logic / shift
| \?\.              # soak access
| \.{2,3}           # range or splat
///
```

or

```javascript
OPERATOR = /^(?:[-=]>|[-+*\/%<>&|^!?=]=|>>>=?|([-+:])\1|([&|<>])\2=?|\?\.|\.{2,3})/
```



## Fancy functions



### jQuery

```coffee
$ ->
	console.log 'And so it begins.'
```

gives

```javascript
$(function () {
	console.log('And so it begins.')
})
```



### Chaining functions

```coffee
$ '#much_win_button'

.on 'click', ->
	evil_corp_bank.receive user_bank.transfer_all()

.text 'You won a goat!'
```



### Chaining arguments

```coffee
id = setTimeout ->
	console.log 'Done!'

, 6000
```



### Functions expecting objects

```coffee
$ '#lil_boxy_thing'

.css
	height: '72px'
	width: '72px'
```



## Stay safe



### Equality

Always `===` and `!==`

```coffee
on == true
yes is on

off != true
no inst on
```



### Existence

```javascript
if person?
	person.say_hi()
```

gives

```coffee
if (typeof person !== "undefined" && person !== null) {
	person.say_hi()
}
```



## CSON anyone?

```coffee
[
	title: 'Fight Club'
	year: 1999
,
	title: 'The Fifth Element'
	year: 1997
,
	title: 'The Matrix'
	year: 1999
]
```

Remember YAML.



## Inspired ES/JS

- [Classes with inheritance](http://coffeescript.org/#classes)

- [Default values for functions](http://coffeescript.org/#literals)

- [Destructuring items](http://coffeescript.org/#destructuring)

- [Generator functions (yield)](http://coffeescript.org/#fat-arrow)

- [List comprehensions/iterators](http://coffeescript.org/#loops)



## LiveScript

[livescript.net](https://livescript.net/)

- "Indirect descendant of CoffeeScript"

- Too many symbols for me, but no hating!



## Why I still use CoffeeScript

- Markdown for comments.

- Reduces noisy characters.

- Encourages me to write simpler code.

- Fits my Jade/Stylus/Python style.



## Want more?

[coffeescript.org](http://coffeescript.org/) is totally worth looking over.



## Thanks!

@MattMS
