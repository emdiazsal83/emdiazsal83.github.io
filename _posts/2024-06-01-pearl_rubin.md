---
layout: post
title: Pearl and Rubin
date: 2024-06-01 23:36:10
description: Two intersecting frameworks for causality
tags: causality
categories: causality
typograms: true
---

In the Functional Causal Model (FCM) framework of causality  {% cite pearl2009causality %} <d-cite key="pearl2009causality"></d-cite> [Pearl, 2009] a system is described in
terms of fundamental processes involving other variables in the system, as well as
random quantities. The processes chosen to describe the system must be fundamental in the sense that 
changes to one of the processes do not affect the others.
Each process variable is modeled by an equation consisting of qualitative elements,
namely the list of cause variables upon which the process depends, and quan-
titative elements, namely the functions describing the relationship between the
process variable and its causes

The potential outcomes framework (PO) [Rubin, 1974] provides a different viewpoint of the
data generating mechanism to that taken by Pearl's FCM approach. We do not use it in this
work but briefly introduce it here so that the FCM framework we adopt for most of the
work presented here can be better understood. We can better grasp the FCM’s strengths
and weaknesses by contrasting its conception of causal phenomena with an alternate
viewpoint. As described, the FCM framework, in a given fixed context (observational or
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
that unit. So we see in the FCM view mechanisms are stable and independent of units
