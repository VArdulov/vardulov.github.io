---
title: 'Learning Koopman Invariant Subspaces for Dynamic Mode Decomposition (A PyTorch Adventure)'
date: 2021-02-05
permalink: /posts/2021/02/lkis-in-pytorch/
tags:
  - free-form
---

Learning Koopman Invariant Subspaces for Dynamic Mode Decomposition (A PyTorch Adventure - Preface)
======

By: Victor Ardulov

I came about to the topic of my research over the course of a couple of life events. Among them was the moment when I 
sat at my desk on campus at UCSC, I thought about [Kalman filters](http://web.mit.edu/kirtley/kirtley/binlustuff/literature/control/Kalman%20filter.pdf) and how they represented a pretty good analogy to how I
approach certain social interactions, the estimation of a persons internal state and the noisy sensor that I collected 
observations through to reconcile the theory of mind. Later that summer and in the subsequent fall, I took my first stroll
through the lands of AI and Machine-Learning, and the concept of embeddings as a way represent seemingly vague and 
non-objective relationships in language or vision as simply a linear operation along a non-linear manifold, invited a 
consideration for how we also do this with other people. This was coupled with my discovery for [Koopman Operator](https://www.mit.edu/~arbabi/research/KoopmanIntro.pdf) and
[Dynamic Mode Decomposition](https://hal-polytechnique.archives-ouvertes.fr/file/index/docid/1020654/filename/DMS0022112010001217a.pdf) which got me thinking about how collecting data on how human conversation was called flow
so could it be possible that fluid-flow modelling techniques could be used to model this as well.

Then I read [The Undoing Project, by Michael Lewis](https://www.goodreads.com/book/show/35631386-the-undoing-project) and contemplated realized that I might have needed to go in pyschology.
One evening while sitting in stupidly hot hotel room in the city of Palm Desert, I started the conversation with my friend
(a professional ballroom dancer) that I loved to instigate with him. I asked him how it was that he knew before anything
even started that certain couples with place in certain positions with few variations in the actual results, however to 
a spectator unfamiliar with the specific couples would not have a reliable method of discerning which of the couples was
better (I was one of said people). What proceeded was long winded (I'm one to talk) take on, well it's not really about 
who dances better, but who knows whom from the organizers and subsequently the judges. I laughed an wondered if I could 
orchestrate a social network manipulation that would allow someone such as myself with limited training in the field 
become a "champion" without actually dancing very well. This *random tangent* turned into the final straw that broke the
camels back. I ended up enrolling in my PhD to apply control theoretic frameworks to human behavior and use them to find
more "optimal" solutions to interaction problems, albeit I was more interested in helping psychologists more effectively
help their clients, not become Victor Ardulov World Star Dance Champion.

Conclusion
---
So this all reads like one of those entries into a recipe that has little to nothing to do with said recipe, but is just
their for AdSense. Well it's a preface for sure, but here I want to outline the point of why I will be doing what I'm doing
and how it fits into my general research work. Over the course of the next few months I hope to work my way through the 
implementation and the math presented in this paper called [*Learning Koopman Invariant Subspaces*](https://arxiv.org/pdf/1710.04340.pdf)

Subject to change but the rough plan is:
1. Re-implement the work done in [LKIS](https://github.com/thetak11/learning-kis) but do it in PyTorch instead of Chainer. Why? Because I see it as opportunity to improve my PyTorch skills, forces me to go through line-by-line of the previous work, and makes my GitHub commits look cooler too.
2. Contemplate how this frame work can be modified to incorporate control explicitly.
3. Try it out and see what it learns
4. Think about alternative models to learn instead from what I could tell in the code and teh paper the NN models aren't
exactly intuitive to me, so perhaps a better model by do better. E.g. embedding projection to learn linearly dynamic subspaces
   