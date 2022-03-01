# Defect Resolution Time

### This metric is a release candidate. To comment on this metric please see Issue # [156](https://github.com/chaoss/wg-risk/issues/156). Following a comment period, this metric will be included in the next regular release.

Question: How much time does a project take to resolve defects once they have been reported and recorded? 

Synonyms: Bug. 

## Description
What is the median time between the report of a defect to the project (using the project’s defect reporting mechanism) and the time where the project resolves the defect? Note the resolution could be to address (resolve and merge) and make the update available to its users or explicitly choosing to not address (reject).
 
Note: 
1. This definition defines the end time as to when the repair is accepted (merged to a public main branch or published) or rejected, as compared to when a formal new release of the software is made (this enables solving a defect where only a few users care about its fixing). For example, a defect to be considered resolved, the closing of the associated report (e.g., issue) must be linked to a merged change request or other change to code including build instructions (compiler flags or other build-time configuration items).
2. Not all reports/issues are accurate, and many accurate reports/issues are not defects (e.g., feature requests & customer support requests).
3. A project may appear to have a rapid response time by rapidly rejecting all defect reports as if the reports do not describe defects. In addition, malicious reporters can create a large number of spurious defect reports. This metric does not try to capture those situations; metrics users should instead see if there are indicators of such practices.
4. Tags used to indicate a defect vary, and defect resolution analysis needs to take into account the labels used on the collection of projects being examined.
5. The intent is not to treat this metric as a Service Level Agreement (SLA) as open source projects are maintained by volunteers and resolution time varies from project to project depending on active maintainers.

Defects include anything in the software that fails to work correctly (e.g., as specified). Deployment issues arising from development operations errors are not considered software defects.

## Objectives
1. To understand how much time transpires between the receipt of a report of a defect and when its resolution is made available to users of the software.
2. To understand mean, median, or other statistical measures of overall defect resolution time for a project, repository, or portfolio in open source projects.
    1. Defect reports often have outliers, e.g., a low-importance defect may be difficult to report, and thus take a very long time to repair. This is why we have recommended median as the primary measure.
    2. Understanding defect resolution across a collection of related repositories, organizations, or projects.

## Implementation
__The usage and dissemination of health metrics may lead to privacy violations. Organizations may be exposed to risks. These risks may flow from compliance with the GDPR in the EU, with state law in the US, or with other laws. There may also be contractual risks flowing from terms of service for data providers such as GitHub and GitLab. The usage of metrics must be examined for risk and potential data ethics problems. Please see [CHAOSS Data Ethics document]() for additional guidance__

Most major Git platforms have “issue trackers”, where feature requests, defects, and deployment support questions are not automatically distinguished from each other. Filters are applied to issues, issue labels, and other metadata to distinguish between defects and other types of issues. 

### Filters 
Include a Filter
* Defect resolution tied to a code change, or [change requests](https://chaoss.community/metric-change-requests/)
* Defect resolution speed measures to indicate the aggregated (average, mean, median) time that transpires between the identification of a defect and its closure via merging a [change requests](https://chaoss.community/metric-change-requests/).  
* Any issue that is labeled as a defect resolution when code is merged into a version available to users (Labels vary by repository). 
* Labels in GitHub, GitLab, Bugzilla, SourceForge, or any other Issue tracking system that indicates the “issue” represents a software defect. 
* Linked issues associated with [change requests](https://chaoss.community/metric-change-requests/), or an indication that no issue is linked to some percentage of [change requests](https://chaoss.community/metric-change-requests/). 


### Visualizations
The Four Keys project can be modified to focus on defect resolution and impact.



![Four Key Project](https://github.com/chaoss/wg-risk/tree/main/focus-areas/code-quality/images/defect-resolution-time_four-key-project.png )

Source: This image is sourced from [Four Keys project] (https://github.com/GoogleCloudPlatform/fourkeys)


![Augur](https://github.com/chaoss/wg-risk/tree/main/focus-areas/code-quality/images/defect-resolution-time_augur-api.png)


Augur’s visualization API can be applied with a filter on defect tags. 


Source: This image is sourced from [Augur](http://augur.chaoss.io/api/unstable/pull_request_reports/Average_PR_duration?repo_id=25440) and http://new.augurlabs.io 


![Grimoirelab](https://github.com/chaoss/wg-risk/tree/main/focus-areas/code-quality/images/defect-resolution-time_grimoirelab-api.png)


Grimoirelab can apply defect related filters to change request data. 

Source: This image is sourced from [GrimoireLab](https://bit.ly/3vftkc1)

### Tools Providing the Metric 

* Grimoirelab 
* Augur 
* Four keys - https://github.com/GoogleCloudPlatform/fourkeys


### Data Collection Strategies 
Collecting issues from an issue tracker, along with corresponding labels, and making a preliminary assessment of whether or not the report reflects an issue. 

## References
1. [Issue Responsiveness]([https://chaoss.community/metric-issue-response-time/](https://chaoss.community/metric-issue-response-time/))  - https://chaoss.community/metric-issue-response-time/
2. [Population]([https://chaoss.community/metric-contributors/](https://chaoss.community/metric-contributors/))[Time to Close]([https://chaoss.community/metric-time-to-close/](https://chaoss.community/metric-time-to-close/))
3. [https://ieeexplore.ieee.org/document/8285884](https://ieeexplore.ieee.org/document/8285884) 

## Contributors

* Duane O’Brian
* David Wheeler
* Kate Stewart
* Renisha Nellums
* Vinod Ahuja
* Sean Goggins
* Sophia Vargas 

***This metric was last reviewed on February 24, 2022 as part of the March 1, 2022 CHAOSS Metrics release review period.***

