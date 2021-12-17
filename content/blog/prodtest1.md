---
title: 'Productivity Test 1'
description: "It's time to improve our workflow"
date: 12/16/2021 12:58:00 -0600 CST
tags: ['productivity', 'blog', 'tech']
---

Every now and then, I like to re-evaluate what all that I use in my workflow, checking on the progress of some promising tools, see what works, what doesn't work, or even what I don't use. This post is going to discuss my workflow with Core and how I update the site. A "Part 2" post will focus on my actual job workflow.

# Writing

I've always loved to write, whether it is something professional or personal, or just because I can. My writings here on Core are for the things I'm passionate about.

What is my process?

First, I have been using [Neovim](https://neovim.io/) for about 2 weeks now and am catching on quickly. Neovim has some amazing plugins for writers, programmers, or people who just want to keep a diary/journal, take quick notes, etc. Most people will probably be turned off by Neovim because, well, it takes after a 30+ year old style of editing text. You can move around with the arrow keys, but it is preferred to use 'hjkl' so that your fingers don't leave home row on the keyboard. Also, it has some amazing keyboard shortcuts to quickly replace words, delete in between special character like quotation marks, incredible searching abilities, etc. I've really enjoyed using it daily for a lot of different things, such as writing scripts, taking notes, practicing some PowerShell techniques, and more.

# Note Taking

My note taking app of choice is [Obsidian](https://obsidian.md/), a Markdown, offline first style "second brain" to capture your ideas and organize them any way you want. The best thing about Obsidian is that even if the app were to go away one day, no problem. You can open your notes (again, it's all Markdown) in any other text editor and you're back to where you were. Obsidian has powerful search built in too so it's easy to search for keywords or tags. I have a note page for blog post ideas so it's easy to quickly jot down an idea when it comes to mind. Markdown is the language of choice with my personal workflow as it is easy to learn, use, manage and backup. IF you've never used [Markdown](https://www.markdownguide.org/cheat-sheet) before, it takes no time to learn the lingo.

# Writing

Once I get some time to start writing, I use Neovim to open a new Markdown file and I start typing away. If I'm really in the mood, I turn on [ZenMode](https://github.com/folke/zen-mode.nvim) for distraction free writing. It's even more pleasant when my [terminal](https://sw.kovidgoyal.net/kitty/) is in full screen mode.

I've been trying to give my writings more time to "bake" instead of just rushing things out in one sitting as I looking back on the content, it does seem . . . well, rushed. But when I feel that the post is good for possible public consumption (I mean, does anyone read this but me?), I simply commit my site to Git. I then log into my Windows server, pull from my Git repo and regenerate my static site using 'npm generate'. Finally, [Caddy](https://caddyserver.com/) will pick up the changes and serve them out to the Internet.

# That's All Folks

Sorry that you may have been expecting some amazing, mind blowing, and life changing workflow here but it's not that complicated; I don't want it to be. I do this for my own fun and fun doesn't have to be convoluted.

In a future post, I will discuss my work workflow, what apps I use, what I do, etc.
