The study of public opinion fundamentally depends on honest responses to survey questions. If a survey respondent feels pressured to respond in ways that please the interviewer or protect her own safety, social scientists will not be able to identify the true population distribution of preferences. If that respondent feels great pressure, she may not respond at all, posing an additional challenge to inference. These issues affect our ability to learn about issues from support for insurgent groups to voter turnout.

Three survey question methods -- *list experiments*, *endorsement experiments*, and the *randomized response technique* -- aim to address this problem by obscuring the truthful response of individuals and thus offer privacy protection to respondents that may encourage honest responses and lower non-response rates. Unlike with direct questions, researchers cannot study the responses of individuals, but each technique remains useful for identifying estimates of the *population distribution* of responses.

For an overview of these methods, see the [five-page survey](http://graemeblair.com/papers/sensitive.pdf) published in the *Comparative Newsletter of the American Political Science Association* (Blair 2015).

This page describes each questioning strategy and regression methods and analysis tools designed to most efficiently explore data from list and endorsement experiments. `sensitivequestions.org` describes the three methods and software packages for `R` that aid in the design and analysis of each technique.


List experiments
---

The truthful answer is to a question is obscured from the interviewer by aggregating the answer with the answers to other questions. The respondent is randomly assigned to the control or treatment group and then the following scripts are read:


> I'm going to read you a list with the names of different groups and individuals on it. After I read the entire list, I'd like you to tell me how many of these groups and individuals you broadly support, meaning that you generally agree with the goals and policies of the group or individual. Please don't tell me which ones you generally agree with; only tell me how many groups or individuals you broadly support.
>
> |---
> | *Control Group* | *Treatment group*
> | Karzai Government | Karzai Government
> | National Solidarity Program | National Solidarity Program
> | Local Farmers | Local Farmers
> |   | **Taliban**
> |===

Resources

* R [`list` package](http://list.sensitivequestions.org), documented on this Web site.
* Methods article in *Political Analysis* (Blair and Imai 2012) describing regression and list experiment diagnostics for several common designs. [pdf](http://pan.oxfordjournals.org/cgi/reprint/mpr048?ijkey=RQ8G4wzSI8vPAEP&keytype=ref)
* Methods article in *JASA* (Imai 2011) describing regression for the standard list experiment design. [pdf](http://imai.princeton.edu/research/files/list.pdf)

Randomized response
--

In this method, random noise is introduced to obscure truthful responses by asking respondents to flip a coin or other randomizing device out of view of the enumerator to determine whether they respond to the sensitive question directly or in a way determined by the randomizing device. In some designs, respondents are "forced" to respond to obscure responses, and in others they respond to a separate innocuous question (see example below). The enumerator sees an affirmative or negative response, but does not know whether the response represents the answer to the sensitive question or whether it was caused by the randomizing device. For example, the respondent first flips a coin, and if she receive heads (tails) she assigns herself to the control (treatment) group.

>|---
> | Control group | Treatment group
> Did your coin land on heads?  |   Have you ever shoplifted?
>  yes / no | yes / no
>|===

Resources

* R [`rr` package](http://rr.sensitivequestions.org), documented on this Web site.
* Methods article in *Journal of the American Statistical Association* (Blair, Imai, and Zhou 2015) describing many randomized response designs, power calculations, and regression methods. [pdf](/papers/randresp.pdf)

Endorsement experiments
--

Respondents' true preferences are obscured by soliciting opinions about a policy position that a sensitive actor endorsed. The interviewer cannot disentangle an individual's preferences for the policy from her feelings about the endorser. The respondent is randomly assigned to the control or treatment group and then the following scripts are read:

>|---
>| *Control group* | *Treatment group*
> | A recent proposal calls for the sweeping reform of the Afghan prison system, including the construction of new prisons in every district to help alleviate overcrowding in existing facilities. Though expensive, new programs for inmates would also be offered, and new judges and prosecutors would be trained. How do you feel about this proposal? | A recent proposal **by the Taliban** calls for the sweeping reform of the Afghan prison system, including the construction of new prisons in every district to help alleviate overcrowding in existing facilities. Though expensive, new programs for inmates would also be offered, and new judges and prosecutors would be trained. How do you feel about this proposal?
>|===

Resources

* R [`endorse` package](http://endorse.sensitivequestions.org), documented on this Web site.
* Hierarchical endorsement experiment regression can be
  implemented with R and JAGS software with the
  [replication archive](http://dvn.iq.harvard.edu/dvn/dv/EndorsementExperiment/faces/study/StudyPage.xhtml?globalId=hdl:1902.1/14840&studyListingIndex=0_00915cc790c795a6350772acdd5d) for Bullock, Imai, and Shapiro (2011).
* Methods article in *Political Analysis* (Bullock, Imai, and Shapiro 2011) describing Bayesian multilevel regression for the endorsement experiment. [pdf](http://imai.princeton.edu/research/files/support.pdf)
* Application in the *American Political Science Review* (Lyall, Imai, and Blair, 2014). "Explaining Support for Combatants during Wartime: A Survey Experiment in Afghanistan." [pdf](/papers/afghan.pdf)
* Application in the *American Journal of Political Science* (Blair, Fair, Malhotra, and Shapiro 2013). [pdf](/papers/pakistan.pdf)

Comparing and combining list and endorsement experiments
--

In a [paper](/papers/listendorse.pdf) in the *American Journal of Political Science* Kosuke Imai and Jason Lyall, we present new graphical and statistical methods for comparing and combining dat  from the two types of experiments with empirical applications from survey in Afghanistan.

