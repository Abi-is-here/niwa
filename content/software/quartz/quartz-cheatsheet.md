---
title: Quartz Cheatsheet
date created: 2024-06-06T22:54
date modified: 2024-08-06T00:25
tags:
- software
---

## For copy-pasting
```
git add content*; git status
git commit -m "Content update"; git push
```

## links

 - [base](https://quartz.jzhao.xyz/)
 - [Eileen's notebook](https://quartz.eilleeenz.com/)
 - [github syntax highlighting](https://gist.github.com/vidaaudrey/14b121a491d889af019e#file-markdown-syntax-highlighting)

## Sync content changes

`npx quartz sync`


### Recommended way

```
git pull
npx quartz sync
```


## Change icons

modify file found in `quartz/static/icon.png`

## Merge changes from upstream

TLDR:

```
git fetch upstream
git checkout v4
git merge upstream/v4
```

h/t [git - How can I merge changes from an upstream branch to my fork's branch - Stack Overflow](https://stackoverflow.com/questions/52981111/how-can-i-merge-changes-from-an-upstream-branch-to-my-forks-branch)

A good practice is to have this structure, which looks like you do, but is good to explain for clarification purposes:

```
origin  https://github.com/your-username/forked-repository.git (fetch)
origin  https://github.com/your-username/forked-repository.git (push)
upstream    https://github.com/original-owner-username/original-repository.git (fetch)
upstream    https://github.com/original-owner-username/original-repository.git (push)
```

So `origin` is your fork and `upstream` the original repository. Then use

```
git fetch upstream
```

And you will get this output

```
From https://github.com/original-owner-username/original-repository
 * [new branch]      master     -> upstream/master
```

where you have now a branch called `upstream/master` which tracks the original repo.

Then checkout to your local fork branch and merge

```
git checkout master
git merge upstream/master
```

> [!warning] To change
> Instead of using `master` as the branch it should be `v4` for Quartz. 

## Preview locally

`npx quartz build --serve`

Only does a hard reload when certain files change, like `quartz.layout.ts`. 

## The reason why 2x components w a script doesn't work

First off, putting it in mobile-only and desktop-only is still instantiating it twice, it just has size 0 when in the corresponding layout. 

Doesn't work because the functions like this:

```ts title='explorer.inline.ts'
function setupExplorer() {
  const explorer = document.getElementById("explorer")
```

So there are two elements with the same ID "explorer" which is NOT ok. 

Similar issue for graphs, except the problem is more with the button to see the full graph view. Oh well. 

## Hiding tags from various components

![[Hiding tags from various components#Summary]]

## For some nice SVGs

[SVG Repo](https://www.svgrepo.com/) 

## Ascii art

[Emoji Combos](https://emojicombos.com/) 


