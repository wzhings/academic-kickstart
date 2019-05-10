+++
title = "Equation derivation procedure for 1.90"

date = 2018-09-09T00:00:00
# lastmod = 2018-09-09T00:00:00

draft = false   # Is this a draft? true/false
toc = false  # Show table of contents? true/false
type = "docs"  # Do not modify.

# Add menu entry to sidebar.
linktitle = "#1-Introduction"
[menu.tutorial]
  parent = "PRML"
  weight = 1

+++

<!--
inline \\(a^2 + b^2 = c\\)
block: \\[ \\]
-->

### Section 1.5.5 in Pattern Recognition and Machine Learning (PRML)

In this note, I will show the derivation procedure of the equation of 1.90 step by step. Before we start, I want to claim that the version of the textbook are 2006 version. The Eq. 1.90 is list on Page 47.

From Page 46 we know, the expected loss can be written as 

\\[\small
\mathbb{E}[L] = \iint\\\{y(\mathbf{x}) - t\\\}^2 p(\mathbf{x}, t)\mathrm{d}\mathbf{x}\mathrm{d}t
\\]

And we know

\\[\small
\\\{y(\mathbf{x}) - t\\\}^2 = \\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}] + \mathbb{E}[t|\mathbf{x}] - t\\\}^2 = \\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\}^2 + 2\\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\}\\\{\mathbb{E}[t|\mathbf{x}] - t\\\} + \\\{\mathbb{E}[t|\mathbf{x}] - t\\\}^2
\\]
In the above equation,

-  for the first term \\\(\small \\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\}^2\\\), we put it back to the expected loss equation and get
\\[\small
\iint \\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\}^2 p(\mathbf{x}, t)\mathrm{d}\mathbf{x}\mathrm{d}t = \int \\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\}^2 p(\mathbf{x})\mathrm{d}\mathbf{x}
\\]
Because we know the marginal probability is \\\(\int p(\mathbf{x}, t)\mathrm{d}t = p(\mathbf x)\\\), and \\\(\small \mathbb{E}[t|\mathbf{x}] \\\) is a *constant* when \\\(\mathbf x\\\) is given.

- for the middle term, \\\(\small 2\\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\}\\\{\mathbb{E}[t|\mathbf{x}] - t\\\}\\\), we can also put it back to the expected loss equaiton. Here we omit the constant number -- $\small 2$ and get
$$ \small
\iint \\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\}\\\{\mathbb{E}[t|\mathbf{x}] - t\\\} p(\mathbf{x}, t)\mathrm{d}\mathbf{x}\mathrm{d}t = \iint \big( \\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\} \mathbb{E}[t|\mathbf{x}] - \\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\}t\big) p(\mathbf{x}, t)\mathrm{d}\mathbf{x}\mathrm{d}t $$
$$ \small
= \iint \big( \\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\} \mathbb{E}[t|\mathbf{x}] \big)p(\mathbf{x}, t)\mathrm{d}\mathbf{x}\mathrm{d}t - \iint \big(\\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\}t \big)p(\mathbf{x}, t)\mathrm{d}\mathbf{x}\mathrm{d}t
$$
In the first term of the above equation, we know $\small \mathbb{E}[t|\mathbf{x}]$ is a constant. Then, the ***first term*** can be written as:
$$\small
\iint \big( \\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\} \mathbb{E}[t|\mathbf{x}] \big)p(\mathbf{x}, t)\mathrm{d}\mathbf{x}\mathrm{d}t = \int \big(\\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\})\mathbb{E}[t|\mathbf{x}] \\\}p(\mathbf x) \mathrm d\mathbf x  
$$
The ***second term*** in the above equaiton can be written as (with joing probability definition $\small p(\mathbf x, t)$):
$$ \small
\iint \big(\\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\}t \big)p(\mathbf{x}, t)\mathrm{d}\mathbf{x}\mathrm{d}t = \iint \\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\}t p(t|\mathbf x)p(\mathbf x)\mathrm{d}\mathbf{x}\mathrm{d}t 
$$
We also know the defintion of $\small \mathbb E[t|\mathbf x] = \int t p(t|\mathbf x) dt$, then the above equation can be written as:
$$\small
\iint \big(\\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\}t \big)p(\mathbf{x}, t)\mathrm{d}\mathbf{x}\mathrm{d}t= \iint \big(\\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\}\big)t p(t|\mathbf x)p(\mathbf x)\mathrm{d}\mathbf{x}\mathrm{d}t = \int \big(\\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\})\mathbb{E}[t|\mathbf{x}]p(\mathbf x) \mathrm d\mathbf x
$$
Then, we know the ***first term*** and ***second term*** are idetical. Therefore, the middle term of the original euqation is just $\small 0$.

- for the last term, $\small \\\{\mathbb{E}[t|\mathbf{x}] - t\\\}^2$ can be insert back to the expected loss euqation and get
$$\small
\iint \\\{\mathbb{E}[t|\mathbf{x}] - t\\\}^2p(\mathbf{x}, t)\mathrm{d}\mathbf{x}\mathrm{d}t = \iint \\\{t - \mathbb{E}[t|\mathbf{x}]\\\}^2 p(t|\mathbf x)p(\mathbf x)\mathrm dt \mathrm d\mathbf x
$$
Here we need to use another time of *Expectation* definition:
$$\small
\int \\\{\mathbb{E}[t|\mathbf{x}] - t\\\}^2p(t|\mathbf x)\mathrm dt = \mathbb E[\\\{t - \mathbb{E}[t|\mathbf{x}]\\\}^2|\mathbf x] = \mathrm{var}[t|\mathbf x]
$$
Then, the last term can be written as following:
$$\small
\iint \\\{\mathbb{E}[t|\mathbf{x}] - t\\\}^2p(\mathbf{x}, t)\mathrm{d}\mathbf{x}\mathrm{d}t = \iint \\\{t - \mathbb{E}[t|\mathbf{x}]\\\}^2 p(t|\mathbf x)p(\mathbf x)\mathrm dt \mathrm d\mathbf x = \int \mathrm{var}[t|\mathbf x] p(\mathbf x) \mathrm d\mathbf x
$$

Therefore, to get the expected loss equaiton of $1.90$, we can have
$$\small
\mathbb{E}[L] = \int \\\{y(\mathbf{x}) - \mathbb{E}[t|\mathbf{x}]\\\}^2 p(\mathbf{x})\mathrm{d}\mathbf{x} +  \int \mathrm{var}[t|\mathbf x] p(\mathbf x) \mathrm d\mathbf x
$$

BTW, for the 2006 version E-book, the last term of Eq.$1.90$ has a typo. It has been fixed at page 7 in the [PRML Errata File](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/05/prml-errata-1st-20110921.pdf). 

-[**END**]-


