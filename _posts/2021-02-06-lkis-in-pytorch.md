---
title: 'Learning Koopman Invariant Subspaces for Dynamic Mode Decomposition (A PyTorch Adventure)'
date: 2021-02-05
permalink: /posts/2021/02/lkis-in-pytorch-part2/
tags:
  - free-form
---

Learning Koopman Invariant Subspaces for Dynamic Mode Decomposition (A PyTorch Adventure - Part 1)
======

By: Victor Ardulov

Abstract
---

Going through the code/paper repeatedly has been highly useful in here I think I will try my best to document what's 
going on in the original paper/code, and then bring up some outstanding questions that I was unable to answer in hopes 
that maybe this way I will be more motivated to figure it out.

Notation
----

So in this paper, the authors introduce notation that is familiar to those that have studied Koopman Operators and DMD 
before. Specifically they outline a dynamical system by grounding it in the following way:

Let $$ s_t $$ represent the state at some time, then for some system there exists a function $$f$$ that describes the 
evolution of the state via, $$s_{t+1} = f(s_{t})$$, then imagine we have some data that we collect via a function $$g$$
that maps the state into a different space where we can actually access, let $$y_t = g(s_t)$$.

They introduce a lot of additional notation, but it's largely to ground the idea in a dynamical system framework. More 
specifically they introduce the notation of $$Y_0 = [g(s_0), g(s_1), ..., g(s_{T-1})]$$ and then 
$$Y_1 = [g(f(s_0)), g(f(s_1)), ..., g(f(s_{T-1}))]$$ you'll notice that from a data point of view, $$Y_0$$ is only a 
single time step shift from $$Y_1$$. 

Finally (for the purposes of this post) they introduce a couple of other ideas. Notably since we cannot directly observe
$$s_t$$ and we don't even really have a good way to guess at the underlying dimensionality they suggest using a neural 
embedding that utilizes a sliding window to predict $$\hat{x}_t = \phi(y_t)$$.

They introduce a reconstruction loss which is simply the mean squared error with regards to the original signal, but the
confusing part to me is that they utilize a network called $g$ that is said to predict $$g(s_t)$$ but then there is another
network $$h$$ that maps from $$g$$ to the domain of $$y$$ which is really confusing me now since before the assumption was
that $$y = g(s)$$. 

