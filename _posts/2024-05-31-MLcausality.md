---
layout: distill
title: Links between machine learning and causality
date: 2024-06-01 15:06:00
description: Causality guides ML through change
tags: Machinelearning causality
categories: causality
citation: true
bibliography: 2024-05-31-MLcausality.bib
---

Test5. Machine learning (ML), and statistics, is, in essence, a field dealing with estimating
probability distributions from data. It is used within causal inference as a tool for learning
observed probability distributions, or properties of these, to learn a directed acyclic graph (DAG, causal discovery)
or estimate an interventional distribution (cause-effect estimation). Since causal inference
is, in effect, a language that may be used to describe the changes a system may endure
and articulate how these may impact the probability distribution of the system, there are
many interesting links with subfields of machine learning which deal with the problem
of learning from data generated in such changing environments <d-cite key="causalML"></d-cite><d-cite key="causality4ML"></d-cite>.

Generalisability and robustness in ML deal with learning a probability distribution
from observed data that is valid for unobserved data. Insofar as any changes in the
data are caused by a changing underlying generating mechanism, causality gives the
language to articulate these changes and decide which parts, or factors, of the probability
distribution need changing. With regard to changes resulting from differing sampling
procedures, more recent developments <d-cite key="BareinboimandPearl2016"></d-cite> also provide the
necessary language to reason about what aspects of the probability distribution change
and which don’t. 

Similarly, co-variate shift and non-stationarity describe situations where
the data distribution of subsets of observations generated at different times has changed.
In the case of a co-variate shift, where the distribution of the inputs changes, knowing
the underlying causal structure can help determine if we should modify our predictive
models in response to this change. If the inputs correspond to the causes and outputs to
effects, then the modularity of the Functional Causal Model (FCM) dictates that this will not influence the conditional
distribution of outputs given inputs. When the prediction task is anti-causal, in the sense
that inputs are effects and outputs are causes, the co-variate shift does necessitate that
the prediction model is changed. 

Something similar occurs in semi-supervised learning, where complementary information about the distribution of the inputs is used in learning
about the conditional distribution of outputs given inputs. This may be fruitful if the
modelling is done in the anti-causal direction. However, if modularity is satisfied in
the causal direction, this cannot help <d-cite key="scholkopfSSL"></d-cite>. 

Transfer learning <d-cite key="transferLearning"></d-cite> [Pan and Yang, 2010], domain-adaptation <d-cite key="domainAdapt"></d-cite>, meta-learning <d-cite key="metaLearning"></d-cite> [Vilalta and Drissi, 2002], and few/one/zero-shot learning <d-cite key="fewShot"></d-cite> [Wang et al., 2020] are families of methods
interested in learning a probability distribution by using large amount of data generated
by one distribution and then using a small amount of data generated with a changed
distribution, to adapt, or update, the estimate. Again, causality can provide the language
to describe these changes and the required conditions to estimate the relevant probability
distributions <d-cite key="invariantTransfer"></d-cite> <d-cite key="domainAdaptCausal"></d-cite>. 

Active learning <d-cite key="activeLearning"></d-cite> [Settles,2009] refers to the problem of choosing how to sample new data in order to improve
our probability distribution estimation. If we can perform controlled experiments, the
active learning prerogative of sampling new data is further extended. Causality gives
us the tools to identify which interventional distributions to sample from, i.e., which
experiments to conduct, to identify the underlying causal structure fully <d-cite key="activeBL"></d-cite> [Toth et al.,
2022]. 

In reinforcement learning, an agent chooses actions in a stochastic environment
to maximize his expected reward. Causal inference can guide the process of knowing
which actions to take to better explore (sample) the different interventional distributions
implied by the FCM that governs the environment <d-cite key="causalRL"></d-cite> [Weichwald et al., 2022]. 

In ML, latent modelling techniques, such as variational autoencoders <d-cite key="VAEs"></d-cite> [Kingma and Welling, 2014],
generally attempt to find a sparse underlying representation, or factorization, of a high
dimensional probability distribution. This is connected to causal discovery since, under
certain specific modularity assumptions, the causal factorization of the joint, corresponding
to the causal DAG is the simplest possible factorization <d-cite key="towardsCausalRep"></d-cite> <d-cite key="disentangledCausal"></d-cite> [Schölkopf et al., 2021, Wang et al.,
2023]. In ML, generative models, such as generative adversarial networks <d-cite key="GANs"></d-cite> [Goodfellow
et al., 2014] or normalizing flows <d-cite key="normFlows"></d-cite> [Rafajłowicz, 2020], generally attempt to describe high-
dimensional structured data as a series of functions in the form of iterative transformations
applied to multivariate noise, where components are mutually independent. These models
effectively estimate an FCM since an FCM can be re-expressed in
terms of only independent noise variables <d-cite key="autoReg"></d-cite> <d-cite key="autoReg2"></d-cite> [Monti et al., 2020, Khemakhem et al., 2020].

Finally, hybrid and physically informed models attempt to incorporate, _a priori_, knowledge
about the phenomenon at hand into ML algorithms which learn from data. From a
causal point of view, this may be incorporated by keeping fixed, known subgraphs of the
causal DAG. Alternatively, when mixed data from different environments are available,
physics-style conservation restrictions may be introduced. In this case, several, possibly
natural, interventions have occurred. Using the modularity assumption of FCMs, we may
enforce those models corresponding to equations not intervened on remain invariant, such
as is applied with <d-cite key="peters2016"></d-cite>.


