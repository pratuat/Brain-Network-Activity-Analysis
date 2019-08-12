# Brain Network Activity Analysis

## Abstract

Neural oscillations are repetitive patterns of neural activity in the central nervous system. In this experiment, two datasets of EEG data for a single subject at rest in (i) eyes-open and (ii) eyes-closed conditions were analyzed. On those datasets, I established the connectivity of the brain signals using two different MVAR Estimators.

## 1. Introduction

Motor imagery (MI) brain-computer interface (BCI), MI-BCI uses the user’s endogenous brain activity in the absence of any external stimuli. MI BCI uses in other words "induced" brain activity from the cortex, rather than ’evoked’ brain activity. The power of BCI resides in their ability to translate the brain activity patterns of a user into messages for an interactive application.
The brain activity processed by the BCI systems is usually measured using Electroen-Ecephalography (EEG). EEG is a technique that measures in real time small electrical currents reflecting brain activity with a device placed on the scalp.
In the following experiment, I studied the differences in the brain activity of a signal at rest for two states: eyes open and eyes closed both at baseline.

## 2. Data

The dataset was downloaded from the PhysioNet Bank and consists of over 1500 EEG recordings, obtained from 109 volunteers. This work is focused on subject 3 for whom two EDF files contained recordings of 64 channels of EEG signals. 2 set of signals were present: one with the subject at rest having their Eyes Open and the other set with the subject at rest having their Eyes Closed.

## 3 Theory and Methodology

Graph connectivity analysis was used to study dynamic functional connectivity (DFC) amongst spatially different brain regions. DFC analysis identifies causal relationship amongst brain regions that exhibits temporal causality in neural activations. There exist numerous estimation models in literature, linear and non- linear, bivariate and multi-variate, that quantifies such causality. Here I have used Granger causality principle based estimators i) Directed Transfer Function (DTF) and ii) Partial Directed Coherence (PDC) to perform the connectivity estimation. We use two-channel multivariate autoregression (MVAR) model to estimate the connectivity in frequency domain and compute pairwise causality index amongst all 64 channels.

### 3.1 Multivariate Autoregressive Model

An autogregressive model assumes that a signal sample X(t) can be expressed in terms of linear sum of **p** previous values of the samples weighted by some model coefficients A and a random error E(t).
p
X(t) = ∑ A(j)X(t − j) + E(t) (1)
j=1
Here, **p** is called modelorder. The equivalent expression of the model in frequency domain is:

>>>>

H( f ) is called transfer matrix of the system that represents pairwise causality relationship between the signals and their spectral charac- teristics.


### 3.2 Directed Transfer Function

Directed Transfer Function (DTF) is a frequency domain estimator introduced by Kaminski and Blinowska, that describes causal influence of a channel on another channel at some frequency. The equation that defines normalized version of DTF measure is.

>>>>

### 3.3 Partial Directed Coherence

Partial Directed Coherence is another spectral measure of directed influence between pairs of Directed Transfer Function (DTF) is a frequency domain estimator introduced by Kaminski and Blinowska, that describes causal influence of a channel on another channel at some frequency. The equation that defines normalized version of DTF measure is.

### 3.4 Frequency Selection

Power spectral density (PSD) analysis was per- formed on all channels to compare the strength of different frequency bands. The PSD estima- tion was done using Welch’s method. As from the figure below, most active signals were ob- served in the **delta (1-4 Hz)** band for **eyes open** state and **alpha (8-12 Hz)** for **eyes closed** state. Hence empirically obtained fre- quencies of 1 Hz and 11 Hz were used to per- form connectivity analysis in further sections.

>>>> 

### 3.5 Statistical Test for Connectivity

In order to rule out the fact that causality may have been discovered between any two signals induced by environmental noise or by chance, we applied statistical p-value test using shuf- fling method. Shuffling method is based upon the generation of distribution of estimators us- ing resampled surrogate data from original datasets. The distribution of estimators were evaluated for each pair of channels for each frequency. Empirical value with significance level greater than 0.05 were considered as true values and rest of the values were set to 0.
Experiments were performed for delta fre- quency band and alpha frequency band, con- sidering target frequencies centered at around 1 Hz and 10 Hz. We produced connectivity graphs for varying network density at 1%, 5%, 10% and so on for both DTF and PDC connec- tivity estimators.

## 4. Results

For connectivity analysis in case I (delta band) analysis, using DTF estimator we ob- served high degree of connectivity around right-frontal lobe in both open and closed eye state while PDC estimator approximates even distribution of connectivity across whole brain region. We do not observe considerable discrepancy in connectivity patterns between open and closed eye state for delta band. Delta wave form are associated to relaxed state of brain. Since the subject is at rest, in absence of any external stimuli in both eyes open and closed state, we see no considerable changes in terms of connectivity in two states.
In case II (alpha band), DTF estimation projects connectivity of the nodes highly lo- calized in right-frontal lobes in eyes-open state but in case of eyes closed state the connectiv- ity is localized more in parietal and occipital regions. This form of slight perturbation in lo- calization of connectivity can also be observed using PDC estimatiors. The increased power in alpha band, as seen in PSD diagram, can be attributed to the phenomenon called ‘alpha blockage‘, the process in which alpha waves decreases and beta wave increases as a subject open their eyes.


