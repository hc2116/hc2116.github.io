---
layout: page
permalink: /code/
title: Projects I have been working on
tags: [code]
modified: 3-10-2014
comments: false
---


<!--It all started when my father taught me some notions of Visual Basic, and with the priceless help of the code completion tool (yeah, no Google at that time). Since then, I've been enjoying coding and here you can find some of the programs I've written. -->



### [DetGen - Generating controllable traffic micro-structures for model probing](https://github.com/detlearsom/detgen)<br>
Model validation through careful model probing of particular importance in Cyber-Security. DetGen is a tool we build to produce traffic with controllable characteristics such as the specific conducted activity, transmitted data length, or experienced congestion in order to attach ground truth labels describing the traffic's computation origin. We use this tool to examine where machine-learning-based intrusion detection models fail to classify traffic correctly and which traffic micro-structures cause this failing.


<center>
<figure class="left"><center>  <img src="/images/DetGen/Eva_Prob2.png" width="300" /> 
<figcaption> Model probing vs evaluation </figcaption> </center></figure>
<figure  class="right"><center>  <img src="/images/DetGen/Docker_setup_final.png" width="300" /> 
<figcaption> Control and monitoring ability of DetGen </figcaption> </center></figure>  
</center>

Some use-cases I examined and am currently publishing examine the inability of a LSTM-traffic-classifier to cope with excessive retransmission sequences, or the coherence of encoder-based traffic projection methods.

<center>
<figure class="left"><center> <img src="/images/DetGen/LSTM_activation.png" width="350" /> 
<figcaption> Influence of retransmissions to LSTM-network. </figcaption> </center></figure>
<figure  class="right"><center>  <img src="/images/DetGen/LSTM_classi.png" width="280" /> 
<figcaption> Classification with and without retransmission. </figcaption> </center></figure>  
</center>

DetGen is available for researchers to use on [GitHub](https://github.com/detlearsom/DetGen).



### [Bidirectional LSTMs for access attack detection](https://hc2116.github.io/docs/MLN20.pdf)<br>
In this project, we want to explore how much we can leverage common sequential network flow structures to create a model that detects low-volume access attacks. The underlying idea is that flow sequences corresponding to individual actions such as web-browsing follow very strong and repetitive structures, such as small HTTP-flows normally being followed by larger HTTP-flows.

<style>
.line{  /* Describes only positioning behaviour */
    display: block; /* Not important, but helpful in this case */
    clear: both;    /* Not important, but helpful in this case */
}

.line__figure{ /* Describes only positioning behaviour */
    float:left;
}

.figure{ /* Describes only view representation. */
    display: block; /* Not important, but helpful in this case */
}

.figure__image{
    background: lightgray;
    width: 400px;
    height: 300px;
}
.left, .right {
  display: inline-block;
}
</style>

<center>
<figure class="left"><center>  <img src="/images/Bi_LSTM/Seq.png" width="220" />
<figcaption> Example input sequence </figcaption> </center></figure>
<figure  class="right"><center>  <img src="/images/Bi_LSTM/LSTM_design_bi2.jpg" width="370" /> 
<figcaption> Model architecture </figcaption> </center></figure>  
</center>
For this, we built a bidirectional LSTM-network with &#8776; 10.000 parameters that learns a language model of flow sequences, with flows acting as word tokens according to their destination port, direction, and size. Our consideration is that these structures can help detect low-volume attacks such as Heartbleed or SQL-injections which deviate from these structures by exploiting vulnerabilities. 

<figure>
<center> <img src="/images/Bi_LSTM/CICplots2-1.png" width="500" />  </center>
  <center> <figcaption> Our detection results - AUC-curves.</figcaption> </center>
</figure>
<!--<center>  <img src="/images/Bi_LSTM/CICplots1-1.png" width="500" /> </center> -->

You can find a corresponding implementation here:
<script src="https://gist.github.com/hc2116/b7bd37d76b892938d32521b484817e2c.js"></script>

### [CNN for stepping-stone flow correlation](https://hc2116.github.io/docs/EvadingStepping-StoneDetection.pdf)<br>
I implemented a deep convolutional Neural Network, inspired by [*DeepCorr*](https://arxiv.org/abs/1808.07285), to correlate connections in a relayed attack. Results were initially very promising, but unfortunately not robust against evasive chaff perturbations, and I have not found a way to overcome this issue. This lead me to perform and publish an [**evaluation**](https://hc2116.github.io/docs/EvadingStepping-StoneDetection.pdf) of several stepping-stone detection methods in the presence of chaff, of which none showed sufficient robustness.

<center> 
<img src="/images/DetGen/DeepCorr.png" width="700" /> 
</center> 

You can find the PyTorch implementation here:
<script src="https://gist.github.com/hc2116/15fcb6ab233b57d004c8aaa154925e27.js"></script>

### [Network traffic activity modelling](https://github.com/hc2116/MMPPsampler)<br>
For my Master's thesis, I developed a fast and scalable Bayesian model that extends traditional Markov modulated Poisson processes to capture the non-Poisson-like bursty nature of network traffic. This model identifies different levels of user network activity automatically, which can be used for detecting abnormal usage patterns.


<center>
<figure class="left"><center> <img src="/images/MMPPsampler/Model.png" width="350" /> 
<figcaption> Model setup. </figcaption> </center></figure>
<figure  class="right"><center>  <img src="/images/MMPPsampler/Results.png" width="650" /> 
<figcaption> Detected activity levels. </figcaption> </center></figure>  
</center>


A fast C++-based implementation for R can be found on my GitHub, and on [CRAN](https://mran.microsoft.com/snapshot/2018-06-01/web/packages/MMPPsampler/index.html). 