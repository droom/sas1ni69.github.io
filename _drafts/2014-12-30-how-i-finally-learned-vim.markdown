---
layout: post
title:  "How I finally learned Vim"
date:   2014-12-30 21:26:52
categories: Web Development
author: Hassanin Ahmed
---

Not everyone learns the same way. Some learn visually, some learn as they do a
The first time I came in contact with a computer was somewhere back in 1996. One day my dad took me with him to the office. No one was around so I sat on a desk with nothing but a computer on it. Since it was company property my dad was reluctant to let me play with it but he said it was okay for me to "play" with the keyboard.

That was the first time I discovered that the alphabets were arranged really weirdly. I couldn't do much other than press the keys which did nothing, I decided to memorize the keys in the way they were arranged, Q to M.

We bought a home computer not too long after. The only thing that I wanted to do was to play with the keyboard! Pretty soon, I was swimming in the land of keyboard shortcuts. Besides copy and paste, the first keyboard shortcuts I learned were for quitting applications and one of my favorites, Ctrl + Esc (Windows). It's an alternative way of launching the start menu.

I no longer use a Windows computer.

``The discovery of Vim.

A few years laters I started getting interested in computer programming and I was introduced to the wonderful world of editors and IDEs. I started with tools like Visual Studio and NetBeans then I eventually moved to non-compiled languages for web development. I started using tools that were lighter and had less buttons like Notepad++. They had all this features that I never used anyways. In my quest for the perfect editor, I came accross a wikipedia article that was simply titled 'Editor Wars'. It immediately put me in a third dimension. Here I was just discovering the one tool that I've been looking for all my life. It combined my love for programming, computer terminals, and keyboards shortcuts. It took me hours to finally get it installed and to type something on it. It was so difficult and unnatural. It was nothing like I was expecting it to be.

Have you ever learned a word and suddenly you start hearing it everywhere? That's how Vim was for me. Suddenly all I could see on the internet was Vim. I tried to learn it. Over and over and over again. Still no luck. Such a complicated tool that had no real guide or manual. The documentation site is a nightmare to use.

There are a lot of tips of how to start working with Vim. Print out a sheet of the most used commands and try not to punch your screen.

I tried Emacs for a while. Worst. They didn't click.

When I started working as a web developer I switched to using an OSX Machine. I instantly fell in love with Text Mate. It was perfect, until I met Sublime Text. That was the ultimate text editor. Shortcuts galore. I could go for hours without really using the mouse on my editor. By this time I was unbelieveably productive with Sublime but at the back of my head, Vim.

I subscribed to countless video tutorials and bought a book or two but none were guides on how to get good with Vim. This was around the time I realized that because there is no one way to get good with Vim, you have to literally struggle. I gave myself countless "use Vim for an entire day, week and month" challenges.

Everytime I got a bit far with Vim, it will do something weird or worse yet, I would run into a configuration problem that I didn't have time to really Google and understand. I will quit. I've quit learning Vim more times than I've tried to quit smoking. They're both equally addictive.

``The learning curve

Here's my problem now. I'm already efficient in another text editor. How do I unlearn one text editor and be just as efficient in another?

Here's what I did to learn and love Vim as much as I always knew I would. I listed down every feature that I used in my daily workflow on a piece of paper and set out to find how to do it in Vim. Here are some of the features that I use daily in both Vim and Sublime Text.


1. Navigate file
2. Replace between parenthesis
3. Delete lines
4. Duplicate lines
5. Move lines
6. Jump between files
7. Navigate tabs
8. Indent code
9. Search file
10. Tree navigation

``Modes
The 3 most common modes that I use are
1. Insert mode, where Vim allows you to insert text.
2. Normal mode, where you write all the commands that aloow you to interact with your file without typing text into it.
3. Visual mode, where you can make visual selections and edits to your text. There is more than one visual mode like Visual Line and Visual Block.

Besides the usual hjkl navigation, I wanted to be able to go up and down the page easily. There are several options.

``Navigation
Move through the file quickly
1. You can use `Ctrl + u` or `Ctrl + d` to move half a screen either up or down.
2. You could type the number of the file followed by gg to go directly to the line
3. /<keyword >You could search for the exact word but note that it will return all the possible options so you'll have to cycle through them if there's more than one.
4. H (High) goes to the top of the screen
5. M (Mid) goes to the mid of the screen
6. L (Low) goes to the bottom of the screen
7. g

Move through lines easily
1. w to move forward 1 word forward with the cursor pointed to the begining of the word.
2. W (shift + w) to move forward 1 word forward with the cursor pointed to the end of the word.
3. b to move 1 word backwards with the cursor pointed to the beginning of the word.
4. B to move 1 word backwards with the cursor pointed to the end of the word.
5. f<character> finds the next instance of the character you're looking for.

``Replace
1. caw (Cut And Write) allows you to delete the word that's under your cursor and to immediately start typing wihout having to press i.
2. ci<tag> lets you change(delete and go to insert mode) everything within the specified tag. This could be (,{,[,<,",' to name a few.

``Delete
1. di<tag> (Delete Inside) lets you delete everything within the specified tag. This could be (,{,[,<,",' to name a few.
2. df<character> (Delete Find) lets you delete everything until the next instance of the specified character, including the character.
3. dt<character> (Delete Til) lets you delete everything until the next instance of the specified character, including the character.
4. daw (Delete All Word) Deletes the word under your cursor
4. x cuts the character that's directly under your cursor
5. dd deletes the line your cursor is on.
6. <num>dd deletes <num> many lines from the line you're on, including the line.
7. D deletes everything to the right of your cursor.
8. J Joins the line below

``Indenting Code
1. == Indents the code to the best of Vim's abilities. This is also dependent on your config and the package. (This sucks with languages that depend on indentation, e.g. Slim, Coffeescript)

``Navigating Tabs
Tabs are not really a native vim feature. You'll need to install a plugin like NERDTree to get going with that.
1. gt moves to the next tab
2. gT moves to the previous tab.
3. <num>gt goes to the tab that corresponds with the number. This is not a 

I
A
i
a
r
s
o

g
G
gg

k

J

:m30

==
<<
>>

cwl
cwh


Once you have gotten over the very basic movements; hjkl and the basic tutorial

``Installing plugins
Plugins are what essentialy turn Vim from a blank canvas into this beautiful editor that you just want to type on.
Pathogen
monokai
ctrl+p
NERDTree

``.vimrc
In my many attempts to learn Vim, the .vimrc was just about the biggest mistake that I was making, over and over. In itself, it sounds like a pretty intimidating thing. Where do I start with it? They say seasoned Vim users have maintained the same configuration for years! How do I take the good stuff and leave out the rest?

The simple answer is unless you know Vim and have experience with the .vimrc file, you're not going to be able to cherry pick the basic configs.

A few attempts later I came accross vimconfiggithubinserthere. Ah! Finally, a beginner friendly, quick-start to Vim config file! Not really. No disrespect to vimconfiggithubinserthere but it is an added complexity. Not only do you have to learn Vim now, you're going to have to learn it in this specific way which you are bound to the .vimrc!

The last time that I tried to learn Vim, I added things to the file myself. It sounds like a big up but it's not. My .vimrc is only 44 lines long and that includes some configs for running Rspec with Vim. You can take a look at it here**insertlinktovimrc**.

Add the things you need. Things like colorscheme, tab spacing and noswapfile were some configs that were really handy. I can easily explain to you every single line in the file. Not because I know so much but because I know so little.

``iTerm 2
One of my favorite things about using Vim in the terminal, is iTerm's ability to hide and be called out from anywhere. With just a simple shortcut (option + space), I can have my text editor on any screen. This is a killer feature for me.

On top of that, with another shortcut (cmd + u), I can toggle the opacity of iTerm, making it easy for me to read or copy any text in a window behind it. How can you say no to that?
