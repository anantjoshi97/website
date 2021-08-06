---
layout: single
title: Research
permalink: /research/
#sidebar:
#  nav: "research"
---

## Research Interests

I am broadly interested in the mathematical theory of control and dynamical systems. My research interests in my undergraduate years have encompassed geometric control and observer design, optimal control and stochastic systems. My first project as a part of PhD has been on applications of methods of observer design to reinforcement learning. A more detailed description of my projects is available below. 
<!--
My time at the student satellite project introduced me to spacecraft dynamics and control.
-->
<! --
A list of my publications is available <a href="{{ '/publications/' | relative_url }}"> here </a>. 
-->

## Particle Methods for Reinforcement Learning

### Background
Reinforcement learning (RL) focusses on solving optimal control problems via model free methods, as opposed to conventional methods which require knowledge of the system model. RL has enjoyed many spellbinding applications, but literature investigating its theoretical aspects is considerably nascent. Our work is an attempt at advancing that front and gain insight into the inner workings of this magical yet mysterious paradigm. 

### Current Work

The focus of our attention is the classic linear quadratic regulator (LQR) problem. LQR is the cornerstone of optimal control theory. Recent efforts in RL have been towards applying traditional methods or inventing new ones, for solving the LQR problem. 

Our work draws inspiration from Kalman filtering, an intricately studied problem in observation theory. Recent advances in Kalman filtering have give rise to particle based methods of filtering. In these methods, an ensemble of particles is passed through a simulator model of the system, and estimates of the system state are produced based on empirical statistics of the particles. This provides a significant computational advantage for very large state spaces. 

We are attempting to leverage tools from duality between control and observer systems, to design model free methods for solving the continuous time LQR problem. We propose an interacting particle system which yields the LQR control gain in a model free way. 

### Preprints
