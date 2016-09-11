---
layout: post
title: Optimizing Indirect Memory References with milk
---
Optimizing Indirect Memory References with milk
=========================================

{% assign authorids=site.data.papers.pact16.authors %}
{% assign lastauthorid=authorids|last %}
{% assign num_authors=authorids|size %}
{% assign num_authors_minus_1=num_authors|minus: 1 %}
{% for authorid in authorids limit:num_authors_minus_1 %} {% assign author=site.data.authors[authorid] %}[{{ author.name }}]({{ author.site }}), {% endfor %} and 
[{{site.data.authors[lastauthorid].name}}]({{site.data.authors[lastauthorid].site}})

## Abstract
Modern applications such as graph and data analytics, when operating on real world data, have working sets much larger than cache capacity and are bottlenecked by DRAM. To make matters worse, DRAM bandwidth is increasing much slower than per CPU core count, while DRAM latency has been virtually stagnant. Parallel applications that are bound by memory bandwidth fail to scale, while applications bound by memory latency draw a small fraction of much-needed bandwidth. While expert programmers may be able to tune important applications by hand through heroic effort, traditional compiler cache optimizations have not been sufficiently aggressive to overcome the growing DRAM gap.

In this paper, we introduce milk - a C/C++ language extension that allows programmers to annotate memory-bound loops concisely. Using optimized intermediate data structures, random indirect memory references are transformed into batches of efficient sequential DRAM accesses. A simple semantic model enhances programmer productivity for efficient parallelization with OpenMP.

We evaluate the MILK compiler on parallel implementations of traditional graph applications, demonstrating performance gains of up to 3x.

## Files
Paper: [[pdf]]({{site.data.papers.pact16.dlpdf}})

## BibTex
    @article{kiriansky:2016,
     author = {Kiriansky, Vladimir and Zhang, Yunming and Amarasinghe, Saman},
     title = {Optimizing Indirect Memory References with milk},
     booktitle = {Proceedings of the 2016 International Conference on Parallel Architectures and Compilation},
     url = {http://doi.acm.org/10.1145/2967938.2967948},
     doi = {10.1145/2967938.2967948},
     series = {PACT '16},
     year = {2016},
     location = {Haifa, Israel},
    }
