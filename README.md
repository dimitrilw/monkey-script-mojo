# monkey-script-mojo

A pass through [Thorsten Ball's interpreter & compiler books](https://thorstenball.com/books/),
but using Mojo instead of Go. If you are interested in replicating this learning project,
then *please* buy Thorsten's books. They are excellent. This readme file serves as a walk-along
for the project and it assumes you have purchased Thorsten's books.

Why am I doing this?
- It is a fun little learning project.
- And because I like Thorsten's books and wanted to go through them again.
- And because I like Mojo's vision and potential.

## special note to Thorsten Ball

I do not presume that you will ever read this. If you do, please know that I have very deep respect
for your work. I am not trying to steal your thunder or anything like that. I am just a fan of your
books and a fan of Mojo. I am doing this for fun and for learning. I am not trying to make money
off of your work. I am not trying to take credit for your work. I am not trying to take anything
away from you. If you wish for me to change this repo in any way, please let me know.

## walking through the book via git-tags

This repo uses tags to denote progress through the book. The tags are named after the sections
in the book and show the state of the code at the end of that section.

These notes are not a replacement for the book. They are a companion to the book.
The notes are written in a way that assumes you are reading the book and using these notes
to understand what differences are happening between the Go code and the Mojo code.
Most code differences are *not* explained in these notes. Rather, I assume that the reader
has a reasonable understanding of the Go language and can understand the differences
between the book's Go examples and this repo's Mojo examples.

## the "Mojo isn't v1" disclaimer

Since Mojo is still rapidly evolving, I plan to add "Mojo version stamps"
to the various book sections, below. My hope is that this helps any reader (including myself)
to understand how the code in this repo relates to the current state of Mojo.

## the "dumdum" disclaimer

I am not a Mojo expert. I am not a compiler expert.  My code will be a disaster.
Follow along at your own risk. Thar be dragons here.

## Writing an Interpreter in ~~Go~~ Mojo

Again, please buy Thorsten's books.
The Interpreter book is available [here](https://interpreterbook.com/).

### 1 Lexing

Until you see another Mojo version stamp, assume all code is written in Mojo v0.1.0.

#### 1.1 Lexical Analysis (tag)

I ran `magic init monkey-script-mojo --format mojoproject` to create the project.

Looking forward, it is worth noting that there will be some differences in project structure.
Thorsten's project uses solid Go file structure. This project will differ in that
it will use Modular's suggested Mojo project structure. All Mojo code will be in the `src`
directory. For example, the lexer code will not be in `lexer/lexer.go`, but rather
it will be in `src/lexer/lexer.mojo`, or maybe just `src/lexer.mojo` (not sure).
In addition, I will use
[Modular's suggested test structure](https://docs.modular.com/mojo/tools/testing/).
This means that test files will not be in the same directory as the code files,
which is a common Go practice. Thorsten's book uses the file `lexer/lexer_test.go`;
at the time I am writing this, I plan for this project to use
`test/lexer/test_foo.mojo` and `test/lexer/test_bar.mojo`.
