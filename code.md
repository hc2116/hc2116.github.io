---
layout: page
permalink: /code/
title: Projects I have been working on
tags: [code]
modified: 3-10-2014
comments: false
---


It all started when my father taught me some notions of Visual Basic, and with the priceless help of the code completion tool (yeah, no Google at that time). Since then, I've been enjoying coding and here you can find some of the programs I've written.

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

For this, we built a bidirectional LSTM-network with &#8776; 10.000 parameters that learns a language model of flow sequences, with flows acting as word tokens according to their destination port, direction, and size. Our consideration is that these structures can help detect low-volume attacks such as Heartbleed or SQL-injections which deviate from these structures by exploiting vulnerabilities. 

<center>  <img src="/images/Bi_LSTM/CICplots1-1.png" width="500" /> </center>
<center> <img src="/images/Bi_LSTM/CICplots2-1.png" width="500" />  </center>

* [**DetGen - Generating controllable traffic micro-structures for model probing**](https://github.com/detlearsom/detgen)<br>

Model validation through careful model probing of particular importance in Cyber-Security. DetGen is a tool we build to produce traffic with controllable characteristics such as the specific conducted activity, transmitted data length, or experienced congestion in order to attach ground truth labels describing the traffic's computation origin. We use this tool to examine where machine-learning-based intrusion detection models fail to classify traffic correctly and which traffic micro-structures cause this failing.

<center> 
<p float="center">
  <img src="/images/DetGen/Eva_Prob2.png" width="300" /> 
  <img src="/images/DetGen/Docker_setup_final.png" width="300" /> 
</p>
</center>

Some use-cases I examined are the inability of a LSTM-traffic-classifier to cope with excessive retransmission sequences, or the coherence of encoder-based traffic projection methods.


<center> 
<p float="center">
  <img src="/images/DetGen/LSTM_activation.png" width="400" /> 
  <img src="/images/DetGen/LSTM_classi.png" width="200" /> 
</p>
</center>


