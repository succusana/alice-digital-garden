---
{"dg-publish":true,"permalink":"/articles/revenge-of-the-blog/","title":"Revenge of the Blog","created":"2025-07-26T14:53:48.581+01:00","updated":"2025-07-26T15:26:50.490+01:00"}
---

So, here we are again... Wait, it's been an entire *year?* 

## How I Procrastinated So Hard That My Website Died

I first made alicealeph.co.uk around a year ago now, in the summer of 2024, and it was *certainly a website*. To get into the technical details a second, the site at the time was being run using [Quartz](https://quartz.jzhao.xyz/), a static site generator that used Obsidian as an editor. This then was pushed to a Github repository, which was then hosted on a Github Pages instance that was hooked into my custom domain. On a basic level, this system worked pretty well! I could write posts, edit them and push them to my website. There was just one problem... For my workflow, the usability was absolutely *trash*.

The problem can be pretty easily seen if I describe the average process of writing a post:
1. Create a new post in the articles folder, mark it as a draft.
2. Write the post.
3. Ensure that the post looks right by going into the command line and typing `npx quartz build --serve`.
4. If it does look right, push that to the repository by typing `npx quartz sync` and wait for that to deploy on the website.

This makes editing on a phone basically impossible, unless you go through the nightmare that is setting up a terminal through something like Termux, linking the Obsidian vault to that and then pulling and pushing git repos, and I'm not even sure if *that* would work considering how locked down Android is nowadays. It also makes editing across multiple devices a right pain, because every single device needs to pull and push the repo before and after every session, although *thankfully* Quartz vaults can be synced using Obsidian Sync. Of course, this doesn't mean that Quartz doesn't have its advantages, since it's far more extensible than basically any other solution that isn't just setting up your site manually.

So, naturally, my website fell by the wayside because it was an absolute pain to edit. Thankfully, I've managed to solve that with my new solution!

## Digital Garden, the Best Kind of Garden

After that whole mess (and eventually migrating my domain to a different provider a few months back, which disconnected the old site entirely), I've been looking for another solution that isn't an absolute misery and doesn't cost an additional £10 a month (as much as I love Obsidian, I already give them £50 a year, soon to be £100+ when I graduate), but unfortunately solutions are lacking. Most people who want to do what I do just use some form of static site generator with Obsidian acting as essentially a fancy text editor, but I wanted something more *built-in* and transferable. That's when I remembered the [Digital Garden plugin](https://dg-docs.ole.dev/): A free, open-source solution that can create a website and publish notes entirely within Obsidian. It does still require *some* setup (namely creating your own Vercel instance and a Github access token, but anyone who actually wants to do this probably knows how to do that already and the guide on their site is pretty easy to follow), but it's far better than what I was doing before.

Now, my workflow is *far* simpler:

1. Open my site's vault.
2. Write an article (with a template already set up for it that adds some important metadata)
3. Publish the note using a command from within Obsidian!

This means that writing isn't an absolute ballache, so I'll almost definitely be updating this site more often now. The only thing I'm missing is an RSS feed... But I'll have to work that out. 

I don't really have much more to say here, but there'll absolutely be some posts here from time to time on whatever comes to mind; I've already got a few ideas that you'll probably see here pretty soon.