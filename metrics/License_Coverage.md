# License Coverage

Question: How much of the code base has declared licenses?

## Description
How much of the code base has declared licenses that scanners can recognize which may not be just OSI-approved. This includes both software and documentation source files and is represented as a percentage of total coverage.

## Objectives
License Coverage provides insight into the percentage of files in a software package that have a declared license, leading to two use cases:
1. A software package is sourced for internal organizational use and declared license coverage can highlight points of interest or concern when using that software package.
2. Further, a software package is provided to external, downstream projects and declared license coverage can make transparent license information needed for downstream integration, deployment, and use.

## Implementation

### Filters
Time: Licenses declared in a repository can change over time as the dependencies of the repository change. One of the principle motivations for tracking license presence, aside from basic awareness, is to draw attention to any unexpected new license introduction.

### Visualizations 

#### Web Presentation of Augur Output:
<img src="https://i.imgur.com/f0kuJlP.png" width="300">

#### JSON Presentation of Augur Output:
<img src="https://i.imgur.com/Xyxm3q3.jpg" width="250">

### Tools Providng the Metric
 1. [Augur](https://github.com/chaoss/augur)

Data can be pulled and filtered to get the desired information. License Coverage data can be found on any [Augur risk page](http://augur.osshealth.io/repo/Zephyr-RTOS/zephyr/risk)

## References
* https://spdx.org/
* https://www.fossology.org
