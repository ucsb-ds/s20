---
num: "lect03"
lecture_date: 2020-04-07
desc: The Data Science Lifecycle and Sampling
ready: true
pdfurl: "https://drive.google.com/open?id=1JIJGlzNv0bsHQKMRUlSyyc9K9B55-ijk"
---


# The Data Science Lifecycle and Sampling

04:08 min into the video

# Announcements

* All the important links are on the website at the top: bookmark the site.
* Instead of directly going to the ds100.lsit.ucsb.edu, use the bit.ly in order to always have it sync with the most up-to-date version

* Homework 1 is due Friday
	* Important: please separately upload pdf only to gradescope assignment titled “Homework 1 PDF only”

* Office hours all week
	* course calendar and schedule on the website

* Tutors attend the lectures: you can ask them questions during the lecture
	* Tuesday: Noemi
	* Thursday: Arthur

* Use the additional Zoom reactions: go slower, etc.

* Due dates on the website will be updated.




# Topics for Today

* Probability review (PSTAT 120A)
* Random variables, probability distribution, expectation and variance
* Review Error, Loss, and Risk and the Relationship between the Data and the “World” (Data science life cycle)
* An Example (10:37 in the video)
	* population
	* sampling frame


Where does randomness come from?


# From Last Week

Key questions:

* What is the population of interest?
* What is the sampling frame?
* How are the data generated?

* These questions are needed for every data analysis, Not just survey data!!

# Where is the randomness?

# Random Variables

* "Informally, a variable whose values depend on outcomes of a random phenomenon” (Wikpedia)

* Possible outcomes of a yet-to-be-performed “experiment”

* Random variables still relevant after conducting the “experiment”. Why?

Probability tells us what could have happened. Useful for contextualizing what did happen.

* Accuracy
* Representativeness

If I can tell you the probability of the sample that I get, then it gives me the notion of the accuracy and representativeness of the samples that I have.

- Big data
- Government agency / company
- non-random sample


Can we make up for no Probability Sample with Big Data?
(Administrative dataset)

# Sample and Population Averages

The gap between these is based on three things:
* Data **quality** measure (how representative is our sampling? Biased sampling?)
* Data **quantity** measure (how big is the sample relative to the population; the "n")
* **Problem difficulty** measure (how variable is the response)

Meng 2018, Annals Applied Probability


# Sample and Population Averages

* Random sampling ensures high data quality by eliminating selection bias and confounding
* When combining data sources for population inferences, those relatively tiny but higher quality sources should be given far more weights than suggested by
their sizes.

* Active Area of Research Area



# Administrative Data on Birth Registration

* Can use large databases of all recorded births

* This is ("big") data. It’s meant to be comprehensive. Is it?

* “Which one should we trust more, a 5% survey sample or an 80% administrative dataset?” (Meng, 2018)
	* For example, 80% administrative dataset = birth certificates for 80% of US families.
(Non-Random)
	* 5% survey sample ==> random

Birth certificates for good of all families in the U.S.?

UNICEF: 1 in 4 children under age 5 do not officially exist. (Discovered via the field work?)

They are not in our administrative data.


# Administrative Data on Birth Registration

* Can use large databases of all recorded births
* Big data, meant to be comprehensive. Is it?


# Large Administrative Data vs Small SRS

A tradeoff between **data quantity** and **data quality** for using sample averages to estimate population averages

Administrative Data - biased, low variance

"The bigger the data the surer we fool ourselves!" (Quote from a recent paper)


# COVID-19 pandemic

* Number of people in the US who tested positive
	* Administrative data from the hospitals
	* Tested positive / US population ==> estimate

Potential problem with this approach?
Lots of undiagnosed people

Germany is doing a SRS: testing a random subset of the population

Randomly testing 20 people gives about the same accuracy that we are getting from the administrative data of those who voluntarily get tested.


# How do we solve probability problems?

33:44 in the video

## Basic Approaches

Review from 120A

Once we have the data, the outcome is determined for that sample, but probability contextualizes how confident we can be about our inference.

* Symmetry and Analogy
* Counting and equally likely
* Trees and conditional probability
* Computer simulation and RNG ("approximate" counting)

# Recall our group of 10 mothers

* Population of 10

* Select a mother at random from the 10, record her number of kids
* Do not replace
* Repeat for a total of 3 samples (n = 3 survey)

What is the chance the second mom that was selected has 1 child?


# Symmetry & Analogy

The above question is analogous to the following problem

* Urn with 10 marble one for each mother,
indistinguishable except for the number written on it
* Box with 10 indistinguishable tickets, except for the number on it (raffle)
* Deck of 10 indistinguishable cards, except for the number on the flip side

4 scenarios indistinguishable "mathematically"

Chance the second draw is 1.


