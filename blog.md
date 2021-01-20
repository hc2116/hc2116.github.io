---
layout: page
permalink: /blog/
title: Personal interests
tagline: Some info on my personal interests
tags: [blog]
comments: false
---

### Research

* [**Bidirectional LSTMs for access attack detection**](https://hc2116.github.io/docs/MLN20.pdf)<br>
In this project, we wanted to explore how much we can leverage common sequential network flow structures to create a model that detects low-volume access attacks. The underlying idea is that flow sequences corresponding to individual actions such as web-browsing follow very strong and repetitive structures, such as small HTTP-flows normally being followed by larger HTTP-flows.

<!-- ![Size distribution of regular HTTP-flows and those immediately subceeding a small HTTP-flow.](images/Bi_LSTM/XSSdist3.png)| -->

<center> 
<p float="center">
  <img src="/images/Bi_LSTM/Seq.png" width="220" /> 
  <img src="/images/Bi_LSTM/LSTM_design_bi2.jpg" width="370" /> 
</p>
</center>