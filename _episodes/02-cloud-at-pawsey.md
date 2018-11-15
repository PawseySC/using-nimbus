---
title: "Nimbus: Cloud computing at Pawsey"
teaching: 20
exercises: 0
questions:
- "How does cloud fit into Pawsey?"
objectives:
- "Understand that different workflows are suited to different compute facilities."
- "Learn that there are different kind of parallel workflows, horizontal and vertical parallelism."
keypoints:
- "Pawsey has a range of compute facilities, cloud, large memory nodes, GPU clusters, HPC clusters."
- "To scale your problem you will need to use horizontal or vertical parallel scaling."
- "Cloud computing with Nimbus has a range of use cases that complement our Supercomputing facilities."
- "Pawsey staff can help navigate through this."
---

## About Cloud
Cloud computing has as many applications as there are algorithms (ie: lots).  However at the Pawsey Supercomputing Centre we are tasked with supporting researchers in Australia to solve complex problems with computational facilities. Using Nimbus can help you scale your problems and make them solvable in a reasonable timeframe.  Is it "Supercomputing"?  We generally reserve such terms to describe our peak computing facilities.  At Pawsey our peak computer is Magnus, a 36000 core Cray XC-30.  It is intended for very large, parallelized workflows that have been specifically designed to run optimally on such hardware.

![Magnus]({{ page.root }}/fig/magnus.png)

> ## What's Cloud Computing?
>
> For collaboration, or when on-demand access is necessary and infrastructure 10s to 100s of cores, 100MB./s transfer
>
> Horizontal scalability (embarrassingly parallel problems)
>
> Training space to promote efficient use of super computers
{: .callout}

> ## So What's Supercomputing?
>
> When research application requires high performance on all levels: 1000s of cores, 60GB/s transfer
>
> Vertical scalability
>
> Analyse projects carefully constructed to most effectively utilize high-end computing infrastructure
{: .callout}

The horizontal scalability here is different from vertical scalability.  Imagine a process that runs on a single compute core;  You could achieve horizontal scalability by running 100 instances of this algorithm, of course trhat might be a lot to manage.  There would be many input files and many output files; you might need to combine these outputs at some point.  An equivalent process tackled with vertical scalability would mean running a single algorithm on 100 cores.  This might result in algorithm that runs 100 times faster (it also might not do so; parallel programming is hard).


At Pawsey Supercomputing Centre we operate a range of computing facilities for a range of computational workflows. Nimbus is well suited to a range of problems in the area of smaller scale problems and horizontally scaled problems.

![The Nimbus Rack Diagram]({{ page.root }}/fig/nimbus_racks.png)

There are (at least) four general groups of researcher use cases that fit well onto a system like Nimbus.

1. Scaling up to HPC
The application process for getting access to Supercomputing can be quite demanding.  You will need to be able to establish to the review committee that you can run your algorithm/s at scale.  You can use Nimbus to develop and refine your parallel workflows and use this work to provide evidence of your experience.

2. The long tail...
We understand that there is great variety in research needs and algorithms.  Most HPC facilities manage access through limited wall time queues.  Usually your compute jobs may be limited to 24 hours before they are killed.  On Nimbus you can run jobs with unlimited execution time (well, as long as your virtual machine is running). This may be important to you if you are running an algorithm where modification to allow for terminating processing is hard or impossible.

3. Complex data workflows
As technologies like the Internet of Things (IOT) and various data capture tools become more common you may be collecting large numbers of various files.  If you then need to write algorithms to sort through this data and analyse it you may end up with some data-bound workflows that are not good use of HPC machines.  HPC facilities are intended for compute bound operations.

4. Clusters in the Cloud
You may need to perform analysis with tools like Hadoop or Apache Spark.  With Nimbus you have access to cluster management tools that allow for growing your cluster elastically and controlling the specifics of the cluster deployment.

## The Benefits of Cloud Computing with Nimbus

| Flexible        |  user configuration and management                                                               |
| On-demand       |  use what you need, delete what you don’t need                                                   |
| Scalable        |  elastically respond to changes in demand                                                        |
| Cost-effective  |  reduce your hardware investment and maintenance costs                                           |
| Accessible      |  available to ALL Australian researchers with minimal application process                        |
| Efficient       |  run applications and analyze your data faster, and in the background – turn your computer off!  |
