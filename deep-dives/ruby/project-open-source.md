---
description: Learn how to make a contribution to an open source project on GitHub.
---

# Project: Open Source

## Introduction

Git basics are very simple, but it sometimes feels like a bottomless pit when you find yourself on the wrong side of a confusing error situation. It's doubly frustrating because you think that messing up or trying the wrong solution can lose data. It's actually very hard to "lose" data with Git but it can certainly be hiding somewhere you wouldn't think to look without an experienced dev poking around.

You'll have your share of misadventures, but everyone does. The best remedy is to commit early and often. The smaller and more modular your commits are, the less that can go wrong if you mess one up.

There's some debate out there about how to properly use Git in your workflow, but we try to think of it this way: Your commit message should fully describe \(in present tense\) what the commit includes, e.g. "add About section to navbar on static pages". If you need to use a comma or the word "and", you've probably got too much stuff in your commit and should think about keeping your changes more modular and independent.

It can also be tempting to immediately fix bugs in your code or tweak some CSS as soon as you see it. Everyone's guilty of that \(ahem\). But it's really best to keep that pen and paper next to you, write down the thing you want to fix, and continue doing what you were doing. Then, when you've committed your current feature or merged its feature branch or somehow extricated yourself from the current problem, go back and tackle the things you wanted to touch originally.

Again, it's all designed to keep your workflow modular and the commits independent so you can easily jump around your Git timeline without messing up too many other things along the way. The first time you need to go back and modify a single monolithic commit, you'll feel that pain and mend your ways.

The thing about Git is that, unless you've got a seriously impressive memory, you can't just learn it by reading about it up front... you need to do it. Find a problem you want to go back and fix, hit an error in your merge, etc. and Google the hell out of it, learning a new Git tactic in the process.

To help you out, come back and refer to this lesson again when you're in trouble. We'll first cover a real-world example of a GitHub workflow used on this very project. The additional resources section below should also help you find high quality resources for when you need them later on.

## Project: Open Source

Let's say you want to contribute to the [open curriculum](https://github.com/TheOdinProject/curriculum/) that this website was based on. How do you do that?

The key players in this story will be the `upstream` \(the original GitHub repository\), the `origin` \(your fork of that repo\), and the "local" repository \(your local clone of `origin`\). Think of it as a happy triangle... except that "local" can only pull from `upstream`, not push.

### **Initial setup**

1. Fork the original \("upstream"\) repository into your own GitHub account by using the "fork" button at the top of that repo's page on GitHub.
2. Clone your forked repository onto your local machine using something like `$ git clone git@github.com:your_user_name_here/curriculum.git` \(you can get the url from the little widget on the sidebar on the right of that repo's page on GitHub\)
3. Because you cloned the repository, you've already got a remote that points to `origin`, which is your fork on GitHub. You will use this to push changes back up to GitHub. You'll also want to be able to pull directly from the original repository on GitHub, which we'll call `upstream`, by setting it up as another remote. Do this by using `$ git remote add upstream git@github.com:TheOdinProject/curriculum.git` inside the cloned folder.
4. If this is your first time using git, don't forget to set your username and email using:

```bash
  $ git config --global user.name "YOUR NAME"
  $ git config --global user.email "YOUR_EMAIL@EXAMPLE.COM"
```

### **Ongoing workflow**

We've got one main branch -- `master`. `master` is for production-ready code. Any code deployed to `master` will be tested in staging and shipped to production. You'll be working in a feature branch and submitting your pull requests to the `master` branch.

1. Create a new feature branch for whatever feature you want to build, using `$ git checkout -b your_feature_name`.
2. Code, commit, code, commit, code, commit \(see a pattern?\)
3. When you're done with your feature, odds are that someone has made changes to the upstream repository in the meantime. That means that your `master` branch is probably out of date. Fetch the most updated copy using `$ git fetch upstream`.
4. Type `$ git branch --all` to see a list of all the branches, including the ones that are normally hidden \(e.g. the remote branches you just grabbed\). You should see `upstream/master` among them.
5. Now merge the upstream's changes into your local version of `master` using `$ git merge`. Specifically, you'll first want to make sure you're on your `master` branch using `$ git checkout master` and then `$ git merge upstream/master` to merge in those upstream changes that we just fetched.
6. Note that a `$ git fetch upstream` followed by a `$ git merge upstream/some_branch` is the EXACT same thing as doing a `$ git pull upstream/some_branch`. We prefer to split it up so we can explicitly walk through the steps.
7. Now that your `master` branch is up-to-date with upstream, you need to merge it into your feature branch. Yes, that is correct and it seems odd at first. Don't you want to merge the feature branch into the `master` branch instead? Yes, you do, _but not yet_. **Your feature branch is dirty.** You don't know if it has any conflicts which might creep up. Any time you are merging in more "senior" branches \(e.g. merging the feature into `master`\), you want it to be a clean and conflict-free merge. So you first merge the "senior" branch into your dirty branch to resolve those conflicts. So do a `$ git checkout your_feature_name` to jump back onto your feature branch then a `$ git merge master` to merge `master` into it.
8. You may have merge conflicts... resolve those with `$ git mergetool` or just manually open up the files that have conflicts. Basically, merge conflicts will insert markers into your conflicting files to denote what lines are part of the incoming code and which lines are part of your pre-existing code. You'll need to manually edit those files one-by-one \(including removing the merge marker text\) and then resave them. Once you've finished fixing all the files that have conflicts, you need to commit your changes to finish the merge.

### **Sending your pull request**

1. Now that your feature branch is squeaky clean and you know it'll merge cleanly into `master`, the hard part is all over. Merge into `master` with `$ git checkout master` followed by `$ git merge your_feature_name`.
2. Now you want to send your local version of the `master` branch back up to your `origin` \(your fork of the `upstream` repository\). You can't send directly to `upstream` because you don't have access, so you'll need to make a pull request. Use `$ git push origin master` to ship `master` up to your fork on GitHub.
3. Finally, submit a pull request to send your forked version of `master` back to the original `upstream` repository's `master` branch. This can be done using GitHub's interface. You just need to make sure you're sending it back to the `master` branch.
4. Shake your moneymaker, you're an OSS contributor!

## Learning outcomes

Look through these now and then use them to test yourself after doing the assignment:

* How often should you commit?
* How large should your commits be?
* What should your commit messages say?
* Can you commit unfinished features?
* Which workflow should you use? \(e.g. Merge? Topic Branches? Git-Flow? Rebase?\) Hint: There's no right answer.

## Assignment

1. Read [Version Control Best Practices](https://www.git-tower.com/blog/version-control-best-practices/) from Tower.
2. Skim Seth Robertson's [Git Best Practices](http://sethrobertson.github.io/GitBestPractices/). Don't worry too much about the commands you haven't seen yet; just work on the high level concepts.
3. Read through this great resource to get a solid understanding of [how git works](http://think-like-a-git.net/).

## Additional resources

This section contains helpful links to other content. It isn't required, so consider it supplemental for if you need to dive deeper into something.

* [Git Branching and Tagging Best Practices on SO](http://programmers.stackexchange.com/questions/165725/git-branching-and-tagging-best-practices)
* [Git Best Practices Workflow Guidelines](http://www.lullabot.com/blog/article/git-best-practices-workflow-guidelines)
* GitHub's [official training site](https://training.github.com/)
* [Understand Git Conceptually](http://www.sbf5.com/~cduan/technical/git/)
* Learn about [Git Branching from Peter Cottle](http://pcottle.github.io/learnGitBranching/) using his interactive branching tutorial.
* Need more still? See [this meta-list of git tutorials for beginners](http://sixrevisions.com/resources/git-tutorials-beginners/).
* [Git Immersion](http://gitimmersion.com/lab_01.html) is another great tutorial to learn the shortcuts of git.
* [Contributing to Open Source](https://youtu.be/mENDYhfxH-o) is a tutorial video reviewing this lesson.

Sometimes \(okay, maybe a lot of times\) when you're working with Git, something goes terribly wrong. Don't panic! Git is designed to help you recover from your misfortune. These resources will help you get back on track towards version control nirvana:

* [Oh sh!t git](http://ohshitgit.com/) is a quick reference to get you out of common Git problems.
* This article on [How to undo \(almost\) anything with Git](https://github.blog/2015-06-08-how-to-undo-almost-anything-with-git/) will walk you through some of many options Git provides for undoing various mistakes.
* If the problem you're facing is more advanced, you can click through [this more in-depth guide](https://sethrobertson.github.io/GitFixUm/fixup.html) to find the answer to your specific question.

