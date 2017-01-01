---
layout: post
title: Useful tool alert, explainshell.com
published: true
---

Ran into this while using the Stack Overflow; [explainshell.com](http://explainshell.com). Basically they take all of Ubuntu's manpages and then parse them so you can paste in any Linux command and then see right away what each option does. Example:

    [rsync -chavzP --stats user@remote.host:/path/to/copy /path/to/local/storage](http://explainshell.com/explain?cmd=rsync+-chavzP+--stats+user%40remote.host%3A%2Fpath%2Fto%2Fcopy+%2Fpath%2Fto%2Flocal%2Fstorage)

It then takes the command you put in there and breaks down each of the flags. I like this for a few reasons. First of all, I hate reading manpages because I'm a human being. This shows me exactly what each option does without having to parse the entire manpage, it only tells me what I care about. Secondly, I prefer to learn by example instead of just reading manpages in their entirety. I can see this tool being very useful for people who are just starting to learn. Command on the internet confusing you? You can at least paste it in here and figure out what it's doing before you end up being [that guy](https://gist.github.com/KartikTalwar/4393116#gistcomment-1947694).  

Another example is [bropages](http://bropages.org/rsync), which lets people submit example commands for each tool, and then users vote on the usefulness of the examples for a nice stackoverflow-like list of example commands. It seems as though they haven't had a commit for almost a year, so not sure if people are still contributing to that, but it seems like a decent enough idea. 
