# Swap words in Emacs

I wind up swapping the order or function arguments all the time (usually because
I've forgotten the correct order for some kind of mapping function). For
example, I just used the lodash function `mapValues` incorrectly:

```JavaScript
mapValues(attrs, (key, val) => sel.attr(key, val))))
```

Typically, I will have to laboriously replace `key` with `val` and `val` with
`key`. But today I stopped myself and checked the Emacs
[docs](https://www.gnu.org/software/emacs/manual/html_node/emacs/Transpose.html). Turns
out, if my cursor is here:

```JavaScript
mapValues(attrs, (key, [X]val) => sel.attr(key, val))))
```

and I press `M-t`, I get this:

```JavaScript
mapValues(attrs, (val, key) => sel.attr(key, val))))
```

Amazing! Vim also supports this kind of word swapping with a
[custom mapping](http://superuser.com/questions/290360/how-to-switch-words-in-an-easy-manner-in-vim)
