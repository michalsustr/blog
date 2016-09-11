---
layout: single
title: Human learning is way more efficient in power consumption... for now.
created: 2016-06-20
categories: 
- neural networks
---
When I was eating dinner a simple thought occurred to me: is machine learning more power efficient than human learning... *from scratch*? 

A neural network called [AlexNet](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf) was trained between five and six days on two GTX 580 3GB GPUs which have [363W consumption](http://www.bit-tech.net/hardware/graphics/2010/11/09/nvidia-geforce-gtx-580-review/8).

So simply calculating, 

$$ W_{GPU} = (5+6)\times 24 \times 363 = 95832\text{Wh}. $$

I found some site that describes [recommended energy intakes for newborn babies](http://www.whfoods.com/genpage.php?tname=specialneed&dbid=7). After some funny discussion we came to conclusion with my mom that I might've been able to perform ImageNet when I would have been 3 years old, so if I take that data, then

$$ W_{human} = 550\times 6\times 30+700\times 6\times 30+1000\times 2\times 12 = 249000\text{cal} = 289.587 \text{Wh}. $$

By comparing these I got to conclusions that humans are about **300 times more power efficient** in learning from scratch. Of course, I took an old version of GPU training so that might differ nowadays (I didn't find other GPU usages quickly, but I knew I would find them in Alex's paper. Maybe someone can calculate this for other nets?). 

Let's assume that energy efficiency has the same [exponential as Moore's law](https://www.technologyreview.com/s/425398/a-new-and-improved-moores-law/) so that it halves every 18 months.
The [GTX 580 launched on 9 November 2010](https://en.wikipedia.org/wiki/GeForce_500_series) so it's almost six years now, and the consumptions should be at the level of 363\times 2^{-4} = 22W. With this consumption it would take in total 6kW. By projecting these numbers human level power efficiency should be achieved by year 2022 - 6 years from now. And with better algorithms it's probably going to be even sooner. Isn't this exciting?

