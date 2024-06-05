---
layout: distill
title: Pearl and Rubin
date: 2024-06-01 23:36:10
description: Two intersecting frameworks for causality
tags: causality
categories: causality
typograms: true
bibliography: 2024-06-01-pearlrubin.bib
---

TEST3. In the Functional Causal Model (FCM) framework of causality  <d-cite key="pearl2009causality"></d-cite> [Pearl, 2009] a system is described in
terms of fundamental processes involving other variables in the system, as well as
random quantities. The processes chosen to describe the system must be fundamental in the sense that 
changes to one of the processes do not affect the others.
Each process variable is modeled by an equation consisting of qualitative elements,
namely the list of cause variables upon which the process depends, and quantitative elements, namely the functions describing the relationship between the
process variable and its causes

The potential outcomes framework (PO) <d-cite key="rubin1974estimating"></d-cite> [Rubin, 1974] provides a different viewpoint of the
data generating mechanism to that taken by Pearl's FCM approach.  We can better grasp the FCM’s strengths
and weaknesses by contrasting its conception of causal phenomena with the alternate
PO viewpoint. As described, the FCM framework, in a given fixed context (observational or
interventional), assumes that the data-generating mechanism involves fixed mechanisms
acting on a given observational unit, mixing its cause and random characteristics to
produce its effect characteristics. Barring any intervention or counterfactual scenario, the
distributions of the cause and noise variables are fixed so that each unit, before it passes
through the FCM mechanisms, can be characterized as an i.i.d. observation of the joint
noise pdf. Equivalently, each unit, after it passes through the FCM mechanisms, can
be characterized as an i.i.d. observation of the joint pdf over the FCM/DAG variables.
Since it is a process point of view, the FCM requires stationarity which is guaranteed by
the fact that an FCM induces a unique joint pdf over the system variables. Additionally,
the modularity assumption provides structural stationarity in that changes to the system
are localized and only affect certain conditional pdfs that make up the joint. In this
framework, causality happens independently of individual observations at the level of the
FCM equations. In the potential outcomes framework, causality happens deterministically
at an individual unit level. A causal effect is defined by the difference between the
intervention/observed (depending on whether the unit was subjected to a controlled
experiment or a natural mechanism) outcome/effect and a counterfactual outcome/effect
(this is why it is also sometimes referred to as the counterfactual framework) resulting
from applying a different treatment or cause-value to the same unit. Note that here
counterfactual does not mean, as with FCMs, that we change the nature of random
quantities at a data-generating mechanism level. Rather it means that we assign a different
cause value to a unit and then observe a deterministic outcome/effect observation for
that unit. So we see in the FCM view mechanisms are stable and independent of units (modularity assumption). Causality is a property of the mechanism, i.e. the arguments of the functions $$f_i$$.  In contrast, in the PO view, it is units that are stable (see stable unit treatment value, or SUTVA, assumption,[Rubin, 1978])) and causality is the process by which assigning treatments/cause-values to units changes effects values of these units.   We cannot observe these individual-level causal phenomena due to the _fundamental causal problem_ [Holland, 1986].. Still, we can estimate the average effect of these micro-causal events on a  population of interest  under certain conditions. In this sense, the FCM framework is process-based, while the PO framework is a population-based approach.  Note the randomness in the PO view comes not from noise quantities participating in the causal mechanism but from counterfactual quantities, which are deterministic but hidden: we would need to observe what effect would have been assigned to a given unit if this unit  had a different cause assignment.  No assumption about the causal mechanism's stationarity seems to be made _a priori_. However, we do not need a stable, stationary causal process since we care about the average causal effect of a population of unobservable causal processes. The implicit assumption seems to be that a unit is characterized by a vector of variables relative to a population. This vector includes all the variables that are causes for _some_ of the units in the population. In other words, since we only care about the average population effect, the population may contain units whose causes and effects result from heterogeneous mechanisms.  Since, in this framework, the desired causal quantity to be estimated is a population property, it is important to account for the differences between the sample and the population that is the object of the causal query. Fulfilment of assumptions, such as _Ignorability/unconfoundedness_ and _positivity/overlap_, determine whether the population causal quantity can be identified, even given infinite data, from the sample. These assumptions take different forms depending on whether the sample is experimental (intervention vs counterfactual definition of causality) or observational (observational vs counterfactual definition of causality). As we can see in the PO framework, there is an implicit assumption that we know which variables – the causes/treatments-  are susceptible  to causally affect another variable (i.e. they are causes in some of the units in the population), the effect, and which variables could confound this effect.  The causal discovery problem does not exist as such in this framework. In a population of interest, the causal variables can never be observed, and in any case, they are not interesting since they may differ across units. We do not ask about the causes of a population but rather what the average effect in a population is. A strength of the PO framework is its emphasis on differences between populations. This can be incorporated into the FCM framework by adding selection variables, which indicate whether a unit of observation is selected for the sample. The augmented FCM can then account for changes between samples not captured by interventions [Bareinboim and Pearl, 2016, Hünermund and Bareinboim, 2019]. In practice, the PO framework is used  when the causes of a variable are relatively well known. The causal inference problem, then, is to estimate the causal effect, such that the focus is on potential differences between the population of interest and the sample used to estimate this causal effect. In this sense, the FCM and PO frameworks are complementary since the former focuses on identifying causes while the latter on estimating causal effects  [Colnet et al., 2020]. For Earth system sciences, the FCM framework seems to be, at least conceptually, more amenable than the PO framework since we often search for stable physical processes/laws that affect the trajectories of physical objects. In other fields, such as social sciences, where laws emerge at the population level and microscopic causal mechanisms may be inaccessible, the PO framework seems more adept at answering interesting causal questions [VanderWeele, 2017].
.
