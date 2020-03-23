---
title: Journal
categories:
- journal 
---


# 2020



## 2020-03 March


### 2020-03-22 Sunday

-   Done two leetcode problems. Largest Rectangle Area is pretty hard. Even you look at the solution with stack, it's still not so intuitive. And the new vimrc was way faster then awesome vimrc, should have done it ealier.


### 2020-03-17 Tuesday

-   set up a hugo blog for leetcode notes. Learned to use git worktree, useful for blogging in gh-pages.

    [leetcode-blog](http://alfmunny.com/leetcode-blog)
    <span class="timestamp-wrapper"><span class="timestamp">[2020-03-17 Tue 21:59]</span></span>


### 2020-03-16 Monday

-   update hexo and note-blog


### 2020-03-15 Sunday

-   用org-hugo搭了一个leetcode的小站。


## 2020-02 February


### 2020-02-18 Tuesday

-   Read the story "Des Kaisers neues Kleid".

    Interesting to learn some words: Pracht, tagen, munter, Beifall, vornehm.
    The irritating one is "versehen".
    It can be use as carrying out, like carrying out his duty.
    Sein Amt versehen. Pretty weird, it also means to mistakingly see something.


### 2020-02-13 Thursday

-   Try the journal out, track my body training with org. I made a video for the training. Got keep it up.

-   搞不出重复任务在agenda上的显示。


# 2019


## 2019-10 October


### 2019-10-24

Never used test data to do model selection. Generate validation set for it.
K-fold Cross-Validation is a cheap way to generate validation sets when the train data is scarce.
Get to know what is generalization error and training error. Overfitting, underfitting and model complexity. “Tunnable Parameters” -> “degree of freedom”. Deep.


### 2019-10-14

\#DLPyTorch4.1 - 4.3. Linear function of a linear function is itself always linear. So we need add some non linearity in to the hidden layer. That is the activation function, so we can’t merge two layers into one. And we get a multilayer perceptron!


### 2019-10-11

\#DLPyTorch3.5 - 3.7. Reread some softmax concepts. Maximum Likelihood Estimation is using product of all posibilities. Consider all events happen independently, what is the best the model that fits all the observations? Plug the observations into the model, calculate the whole prosibility of it, and maximize it. It’s basic. Is linear model always a fully conntected layer? Seems to be.


### 2019-10-10

\#DLPyTorch3.4 Softmax Regression for classification problems. Use the maximum likelihood estimation to get the loss function. As an intuition, softmax regression is like to add one more layer(softmax function) over the multiple linear regressions.

For n categories, we have n linear regressions. And then convert the n outputs to a distribution(Softmax).
To compare with the known distribution(calculated from labels), we use the Cross Entropy as the loss function. (Mean Square Error for linear regression)


### 2019-10-08

Deep learning is too deep. Should have done some serious programming and reading, end up in making this notes site to work, and write about 'About'. \`site.categories.findOne({name: "notes"}).posts\` saved the world.

