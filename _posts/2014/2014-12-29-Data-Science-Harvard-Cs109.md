---
layout: post
title: Data Science
categories:
- Programming
- Machine Learning
- Tools
tags:
- Markdown
- Algorithm
- C
- Scikit
- Python

---
* Data Visualization
* Bayesian and Frequentist
* section2

---

Click [here](https://github.com/jakevdp/sklearn_pycon2013) for a  nice introduction ipython notebook of the sklearn package.

## Data Visualization
I choose the picture from web to show which method we should use to visualize our data. We should never use a 3-D plot to visualize data and instead use color or shape to mean other dimension. We often think a rainbow is a good choice for color map but it is in fact not so effective as many other color map provided in brewer2mpl. This cool [website](http://colorbrewer2.org/) shows kinds of color map which has been proved useful for sequential qualitative or diverging data.  
![Visualization](/png/visualization.png?raw=true)  
In this case, we need to show the rainfall for each province and I choose color to visualize the number. It is sequential data and we can need one color map from the website.  
![RainFall](/png/2012RainFall.png?raw=true)
Use *fill* function provided in the matplotlib, and choose colormap from brewer2mpl. We can fill the area and choose the color according to some number by using Normalize function in mpl.colors.



## Bayesian and Frequentist
- Bayesian: Assume the parameters that we are interested in have some kinds of distribution. We use $$\pi(\theta \vert y)$$ to denote the posterior distribution. If we consider the posterior distribution, it is not hard to find the connection between the distribution and likelihood function. If we consider interval estimation, we can find the interval, e.g. $$P(\theta \in (-2,5) \vert y)=0.95$$, because we can calculate the posterior distribution for the parameter. Common prior distribution to choose is conjugate priors to simplify our calculation. But due to the fast computers we have, we use MCMC to simulate the procedure.

- Frequentist: Never use $$\pi(\theta \vert y)$$. They tend to assume there are given value for the parameter we want to estimate. The $$\theta$$ should be fixed and unknown. When it refer to confidence interval, for example 95% confidence, we cannot have the same notation as Bayesian and it does not mean that the parameter will lie in this interval with probability 0.95. In fact, it means that it is 95% true that the interval will cover the true parameter. We can treat the CI as some long time estimation, for example FDA will check thousands of drugs every year and they want to control the error rate.

##Interesting trick
- Consider the regression line y=cx and x=ty. if dataset are normalized and standardized, c and t should be the same even though according to math c should be 1 over t. This is called regression to the mean.
- Data in high dimensional space tends to lie in the boundary of the circle. An intuitive explanation is that as long as any component of the random vector near 1, the square sum will near 1 which means that the point lies in the boundary. The volume of a circle  over the volume of a cube tends to decrease when the dimension d increase.
- Example, we have 100 sample and each sample has 1000 feature. We want to choose a model using cross-validation. Should we select features first or select features within the CV process? Do variable selection in the CV process, because if we do variable selection first according to the whole dataset, the error rate will be trick by using CV because these features are decided by the whole dataset.
- Think like a Bayesian. When you see hear someone speak cantonese ? Do you think where he come from ?  From HongKong or not ? Please think like a Bayesian ~. Or when you watch a high level football game and the team you support has been defeated by 0:7 and you may think they even do not play as well as I do. What is the possibility of this event ?
- Determinists vs Probabilists "We may regard the present state of the universe as the effect of its past and the cause of its future. An intellect which at a certain moment would know all forces that set nature in motion, and all positions of all items of which nature is composed, if the intellect were also vast enough to submit these data to analysis, it would embrace in a single formula the movements of the greatest bodies of the universe and those of the tiniest atom; for such an intellect nothing would be uncertain and the future just like the past would be present before its eyes". From Simon Laplace. Probabilists tend to think things are knowable with some degree of uncertainty. God plays dices and **perfect** conditions are impossible if the universe itself is random.
- Chaos theory in dynamic system shows certain types of systems are very hard to predict. Lorenz found 3.967 and 3.9669 for initial value may lead total different outcome in his weather prediction model. But in reality, when catastrophe strikes, we look for evidence that may explain the chaos. For example, Giuliani was lucky to predict earthquake, the monkey typed shakespeare and the octopus predicted the WorldCup.
- Overfitting. John Von Neumann saied: "With four parameters, I can fit an elephant, and with five I can make him wiggle his trunk". Overfitting makes our model look better on paper but perform worse in the real world. What we want is to seek an overly specific solution to a general problem. We balance what the data tells us. Michael Babyak said: "In science, we seek to balance curiosity with skepticism"
- Most of time, when an economic prediction is presented, however, only a single number is mentioned. They see uncertainty as the enemy -something that threatens their reputation. In fact, the distribution of the prediction is so important. An oft-told joke: a statistician drowned crossing a river that was only three feet deep on average. What if we know the distribution of the depth ?
- "Correlation does not imply causation." This is so significance when we work on lots of variables. How creative you might be when you have a stack of economic variables as thick as a phone book? A once-famous "leading-indictor" for stock market is the winner of the super bowl ! We can pick up variables from real world to establish connection with stock market. Another example is ice cream sales and forest fire alarm increase when it is hot.
- When we observe some variables, they may will not be good indicators. At its logical extreme, this is a bit like the observer effect. Boss treat the time when workers come to the office as a good indicator to measure how hard they work. However, once told, workers may go to office earlier to surf the internet or eat breakfast. In his way, he has to change his variable.
- Rational bias: The less reputation you have, the less you will lose by taking a bigger risk when you make a prediction. Even if you know that the forecast is dodgy, it might be rational for you to go after the big score(this looks like risk function). Even if you know that the forecast is dodgy, it might be rational for you to go after the big score. Conversely, if you have already established a good reputation, you might be reluctant to step too far out of line even when you think the data demands it. Sometimes, there are consumers for these ideas. In economic, the line between economic forecasting and economic policy is blurry, a bad forecast can make the real economy worse.
- [Gambler's ruin](http://en.wikipedia.org/wiki/Gambler%27s_ruin): Even in a fair casino, you will lose all your money with probability 1, if you do not stop gambling. According to discrete Markov theory, the probability of ruining will be 1 when the wining probability p equal to losing probability q, not to mention p is less  than q. An intuitive explanation is to image you gamble with someone with a fair coin and with fair $100. What if your opponent has $200 or even unlimit money(the casino)? Refer the [quora answer](http://www.quora.com/What-is-an-intuitive-explanation-of-the-Gamblers-Ruin-result)
