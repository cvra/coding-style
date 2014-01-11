# CVRA Coding Style

## Whitespace
* Indent with 4 spaces, not tabs.
* End file with a new line (as requested per C99 standard).
* Use empty line to divide code into logical chunks.
* Put spaces around operator : `x <= 2 && y > 10` is way easier to read than `x<=2&&y>10`.

## Placing braces
For this, we will follow the good old prophets of C : Kernighan and Ritchie.
It also happens to be the rule of the Linux Kernel.
The way the prophets taught us is to put the opening brace last on the line and the closing brace first :

```cpp
if(x == 42) {
    // do stuff
}
```

Note that the closing brace is always on its own line except if it is followed by a continuation
of the same statement, for example in a `do..while` block or in an `if..else` block :

```cpp
if(x == 42) {
    // do stuff
} else if(x == 34) {
    // do something else
} else {
    // do yet another thingie
}
```

```cpp
do {
    // do stuff
} while(x < 42);
```

The only exceptions to this rule are functions : the opening brace should be on its own line.
Of course, this is inconsistent, but :

1. Kernighan and Ritchie cannot be wrong, right ?
2. In C, functions are not standard blocks : they cannot be nested.

So functions definition look like this :

```cpp
void do_something_useful(void)
{
    // Code goes here
}
```

## Naming conventions
* Do *not* use CamelCaseNotation, use underscore_notation instead.
* Short variable names are ok if they are still understandable : `i` is ok for a loop counter, but `foo` for a function name isn't.
* If you *really* need a global variable, but it can live with file-only scope, declare it with the `static` keyword.

## Vim users
To have the same indentation convention as used here, put the following in your vimrc :

```VimL
" 4 space indentation"
set expandtab
set shiftwidth=4
set softtabstop=4
```

## Suggestions
In case you disagree with the following proposal, please open an issue / pull request so we can discuss it.
