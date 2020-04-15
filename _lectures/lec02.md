---
num: "lect02"
lecture_date: 2020-04-02
desc: Data Life Cycle
ready: true
pdfurl: "https://drive.google.com/open?id=1JIJGlzNv0bsHQKMRUlSyyc9K9B55-ijk"
---

Lecture 2


# Announcements

* Office hours begin today. Schedule here: https://ucsb-ds.github.io/s20/info/staff/

* Lecture recordings should be accessible when using UCSB netid.
* Use the same zoom link for lab and office hours
* Try submitting first lab to Gradescope by 5pm Friday.
* Homework 1 out in the next 1-2 days.

Question: "No required application" installed on the computer when downloading the notebook. How to open it? We'll try to resolve it before the end of the week.


# Data Life Cycle

Continuous loop that starts with trying to get the insight into the data.

1. Question Formulation
2. Data Design/Generation (experimentation)
3. Data Analysis (EDA, visualization)
4. Generalization

* Refine the question and repeat the process.

* Step 1 along with step 4 are crucial but the focus of this class, is step 2 along with step 3.


# START SIMPLE

QUESTION:
What is the typical family size (children only)?

Want to understand our population (family size); get out the survey to collect samples; get the data and then generalize to the population.

Probability (sampling distribution)
==> Data
"Statistic"
Inference (estimation, hypotesis testing)
==> Population



# DATA:
Survey of all 250 students at UCSB and asked their family size

A single sample / counts.


# ANALYSIS

Bar chart / histogram visualization
provides a quick summary of the distribution

Can we provide a summary statistic?

One number, simple numeric summary

What number should we choose?
Mean, median

# DETOUR:
Why is the sample mean such a desirable summary?

# Summarizing the Data

* DATA: x1, x2, ..., xn where n is 250 in our example
	* Want a single numeric statistic; let's call it c.

* ERROR: x1 - c, x2, ..., xn
	* (The difference between the family size xi and summary statistic c)

* LOSS function: takes real numbers (error) and maps the error to positive numbers (the cost of making an error).

Example:
```
x1 = 2, c = 2, so the loss L is 0 (x1 - c)
x2 = 4, c = 2, so the loss L is 2 (x2 - c)
```

## Average loss aka empirical risk
Empirical, because we are looking at the observed sample

Minimize the empirical risk: want to minimize over all c, solve the minimization problem (sum over all losses)

**What's a reasonable loss function to use?**

* positive, increasing function
* MSE: (mean) squared error


# Minimize the Average Loss

Squared error loss properties:
* maps to positive values
* continuous function (and continuous derivative, i.e. "smooth")
* deep connection to gaussian/normal

Over all possible values of summary statistic, c, minimize the squared error

Q: Isn't it the formula for the variance?

(c can be arbitrary, so it's not quite the variance; see below)


# Refresher

"Sample mean" (x bar): Linear operation

**Linear operation property**: Scaling and shifting each observation scales and shifts the sample mean.


# Minimize the Average Loss

**How to minimize a function?**
Look for the place where the derivative is 0.

Calculus + algebra skills FTW!

Shows that c = the sample mean

When L is the squared loss, c = x-bar minimizes the loss; empirical risk

What does the empirical risk look like?

- expected value

# The Sample Average Minimizes Empirical Risk

Less than or equal to any other loss function that uses c, which can be arbitrary, so the empirical risk is not quite the variance, unless our c is the mean.

Specific for the squared loss function. If that's not the loss function, the result might/will be different.

# Data Life Cycle

1. Question Formulation (Family size)
2. Data Design/Generation (survey)
3. Data Analysis (loss function + minimizing risk --> got "c")
4. In some cases we do not want/need to generalize.

If we have data for **all** individuals, we don't need to generalize. ==> "Finite sample inference"

What does our data say about larger population?

# Consider the Question Carefully

* What is the typical family size (children only)?

Families: all shapes, all sizes

Angelina Jolie: 3 adopted and 3 biological children.

* How well can we measure this?
* What are we trying to measure?

Who do I pick to figure out the measure?


# Focus the Question

Questions for our question to help us focus:

* WHERE
*  WHEN
*  WHO
*  WHAT

From Female Fertility Perspective:
To estimate the number of children that a woman gives birth to.

* WHERE: in the USA
*  WHEN: in 2015
*  WHO: Females, aged 40-44 (likely they've had all the children they are going to have)
*  WHAT: number of births

* Q2: how does it compare to births 50 years ago?


# Focus the Question

The Question gives focus to the **Population** that we want to study.



# Data Life Cycle

Back to our diagram.

Population: women in USA in 2015.
Survey them and make a larger inference about the population.


# How well does UCSB represent the
group of interest?

* Mothers of children at UCSB
* Measure the mothers via the children
* Mothers who are 40-44 in 2015

How might these characteristics impact the
estimate of the number of children a US woman bears in her lifetime in 2015?

Bias up, Bias down, No impact


### Breakout discussion results
42-45 min into the video

* Multiple siblings on campus: their family might be represented multiple times
* The survey doesn't account for Women with no children
* Not representative of the Demographics: wealth, race, etc. (factors that affect the number of children a woman had)
* Age: 40-44? Having children at age 20-24 (to have their children in college)?

* What kinds of bias? Over/underestimation?

"size Biased sampling" (multiple siblings)

(Positive bias, we'll overestimate)

# According to Pew Research Center

Women with less education tend to have more children.

26% with high school diploma have 4+ children vs. 8% of women with the postgraduate degree

How might this impact
the class average?

http://www.pewsocialtrends.org/2015/05/07/family-size-among-mothers/

The data used in these analyses are
designed to assess women’s fertility, and as such a “mother” is here defined as any
woman who has given birth. However, many women who do not bear their own children are indeed mothers.


# Population of Interest

* Population of interest (All women in 2015 in USA)
	* The individuals that we want to study

* The Sample is a subset of the Frame
	* Mothers of UCSB students

* Individuals who aren't reachable through the sampling frame
* Individuals not in the population

Sample: how we select individuals from the frame.

# Possible case

All the same:
Sample = Sampling Frame = Population

Where/when have we recently seen this?
- class survey
- Census!

Who are we missing? How might this affect our results?


# Common Assumption when sampling

Sampling Frame = Population

Scenario: Access to all members of the Population when sampling

(Common Assumption)


# Administrative Data

Sampling Frame = Sample

Government data: e.g., birth certificate


# Most common scenario

Little overlap


# How are the data generated?

* What is the population of interest?
* What is the sampling frame?
* **How are the data generated?**

It doesn't matter what fancy tools / analyses you use unless you understand where data came from?


# DETOUR:

1. The simple random sample

2. Why is a probability sample
so desirable?

# The Simple Random Sample (SRS)

* Suppose we have a population with _N_ subjects
* We are able to sample _n_ of them
* **The SRS is a random sample where every unique subset of n subjects has the same chance of appearing in the sample**
* This means each person is equally likely to be in the sample ("N choose n", N! / n! (N-n)!)

Example for N = 4 and n = 2, gives 6 possible outcomes.


# The Advantages of a SRS

* Representative: The sample tends to look like the population
* Statistics based on the sample tend to be close to statistics based on the population
* We can provide typical deviations of sample statistics from population values.
* AND MORE...

## Start Simple

Suppose our population contains only 10 mothers and we take a **Simple Random Sample** of 3 for our survey.

A table with true numbers.

10 choose 3 possible samples (120 possible samples)

If I got "unlucky", I chose 2 mothers with 1 child and 1 mother with 2. (Why "unlucky"? Because I selected the individuals with the smallest number of children and my representative sample is much smaller than the true values in my dataset.)

Can I compute the chance of getting "unlucky"? That's what we did in 120A and what 120B gets at.


## Formal Set Up

Like a Lotto Ball machine with the number of children as the number on the ball.

Drawing them without replacement

X1: The number of children for the first mother chosen
X2: The number of children for the second mother chosen
X3: The number of children for the third mother chosen

Random variable: we don't know what we'll get.

Truth table

Probability Distribution

What is the _expected value_ of X1?
* Sum over all possibilities times the probability of that possibility (from the truth table).
* On average, in our example, the family size is 2.3


# Wrap-up

Key questions:
* What is the population of interest?
* What is the sampling frame?
* How are the data generated?

Where is the randomness coming from?


---



# DETOUR CONTINUED:
Why is the expected value a desirable summary of a probability distribution?

## Random Variables

Random Variables:
Random ERROR:
LOSS:

## Summarizing the Probability Distribution

EXPECTED LOSS:

AKA RISK

Minimize the risk

Properties of Expected Value

The Expected Value Minimizes Risk


Can we make up for no Probability Sample with Big Data?
