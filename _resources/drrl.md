---
title: Diabetes-Related Reinforcement Learning
short_name: DRRL
order: 1
summary: >-
  Reinforcement learning for insulin dosing and glucose control: simulators,
  starter code, and prior work to get a project off the ground.

# ---------------------------------------------------------------------------
# STARTER ENTRIES: well-known public resources, added as examples.
# Check each one and add or remove entries as you like.
# ---------------------------------------------------------------------------
repos:
  - name: simglucose
    url: https://github.com/jxx123/simglucose
    language: Python
    description: >-
      Open-source Python implementation of the FDA-accepted UVA/Padova 2008
      T1D simulator, with a Gym-style interface for RL.

works:
  - title: "Deep Reinforcement Learning for Closed-Loop Blood Glucose Control"
    authors: "Ian Fox, Joyce Lee, Rodica Pop-Busui, Jenna Wiens"
    venue: "Machine Learning for Healthcare (MLHC)"
    year: 2020
  - title: "Offline reinforcement learning for safer blood glucose control in people with type 1 diabetes"
    authors: "Harry Emerson, Matthew Guy, Ryan McConville"
    venue: "Journal of Biomedical Informatics"
    year: 2023
---

T1D is a chronic disease in which the body can no longer produce insulin, the
hormone that regulates blood glucose. People with T1D must supply insulin
themselves, either through injections or an insulin pump. Many pumps run a
control algorithm that delivers insulin automatically, but mostly only the
small, steady amounts needed throughout the day, known as *basal* insulin.
Larger doses given for meals or to correct high blood glucose, known as
*boluses*, are still largely left to the patient.

This leaves the most consequential part of managing the condition to the
person with T1D, and mistakes have real costs: blood glucose that runs too high
([hyperglycemia](https://en.wikipedia.org/wiki/Hyperglycemia)) or too low
([hypoglycemia](https://en.wikipedia.org/wiki/Hypoglycemia)). My main interest
is offline reinforcement learning for insulin control, which learns dosing
policies from logged data rather than trial and error on real patients.

### Where DRRL fits

It can be hard to place this work within the broader landscape of CGM- and
insulin-based models and decision making. On one side is the growing body of
work that uses CGM data for general downstream tasks, such as the foundation
model [GlucoFM](https://arxiv.org/pdf/2605.30865). On the other are
insulin-dosing RL problems outside diabetes, such as insulin delivery in the
ICU. I think diabetes-related reinforcement learning (DRRL) should be treated as
a class of its own, and it is the primary focus of my research. Work outside
DRRL is still worth following, since many of its ideas carry over to these
goals.
