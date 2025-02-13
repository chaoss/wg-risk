# Defect Resolution Duration

**Question:** How much time does a project take to resolve defects once they have been reported and recorded?

## Overview

Defect Resolution Duration measures the median time between the reporting of a software defect and its resolution, either through code changes (merged fixes) or rejection of the report/issue.  Resolution times across contributors issues or reports may highlight whether contributors are facing delays in getting their reports/issues addressed.  Each data point is tied to a defect report/issue and its corresponding resolution action.
When defect resolution takes a fast turn, it indicates an active and responsive maintainer team on a project, which contributes to overall software quality and user satisfaction. Understanding defect resolution across a collection of related repositories, organisations, or projects helps assess performance,  allocate resources more effectively to address the most critical issues,  streamline workflows and improve efficiency, and assess the level of contributors engagement and participations. Defects include anything in the software that fails to work correctly (e.g., as specified). Deployment issues arising from development operations errors are not considered software defects.

## Want to Know More?

<span markdown="1"><details>

<summary>Click to read more about this metric.</summary>

### Data Collection Strategies

Collecting issues from an issue tracker, along with corresponding labels, and making a preliminary assessment of whether or not the report reflects an issue.

### Filters

*   Defect resolution tied to a code change, or [change requests](https://chaoss.community/metric-change-requests/)
*   Defect resolution speed measures to indicate the aggregated (average, mean, median) time that transpires between the identification of a defect and its closure via merging a [change requests](https://chaoss.community/metric-change-requests/).
*   Any issue that is labeled as a defect resolution when code is merged into a version available to users (Labels vary by repository).
*   Labels in GitHub, GitLab, Bugzilla, SourceForge, or any other Issue tracking system that indicates the “issue” represents a software defect.
*   Linked issues associated with [change requests](https://chaoss.community/metric-change-requests/), or an indication that no issue is linked to some percentage of [change requests](https://chaoss.community/metric-change-requests/).

### Visualizations

The [Four Keys project](https://github.com/GoogleCloudPlatform/fourkeys) can be modified to focus on defect resolution and impact.

[Grimoirelab](https://bit.ly/3vftkc1) can apply defect related filters to change request data.

![Grimoirelab](https://github.com/chaoss/wg-risk/blob/main/focus-areas/code-quality/images/defect-resolution-time_grimoirelab-api.png)

</details></span><br>

## References

1.  [Issue Responsiveness](https://chaoss.community/metric-issue-response-time/)
2.  [Time to Close](https://chaoss.community/metric-time-to-close/)
3.  <https://ieeexplore.ieee.org/document/8285884>

## Contributors

*   Duane O’Brian
*   David Wheeler
*   Kate Stewart
*   Renisha Nellums
*   Vinod Ahuja
*   Sean Goggins
*   Sophia Vargas
*   Peculiar C Umeh

## Additional Information

To edit this metric please [submit a Change Request here](https://github.com/chaoss/wg-risk/blob/main/focus-areas/code-quality/defect-resolution-duration.md)

To reference this metric in software or publications please use this stable URL: <https://chaoss.community/?p=4727>

<!-- # For groupings in the knowledge base
Context tags: Software 
Keyword tags: risk, defect, resolution, issues, issue, issues open, issues closed, defect resolution, bug
-->
