# Contributor Absence Factor

Question: How high is the risk to a project should the most active people leave?

## Description  
The Contributor Absence Factor is a compelling metric because it visualizes the question "how many contributors can we lose before a project stalls?" 

The Contributor Absence Factor is the smallest number of people that make 50% of contributions.

This metric was previously called "Bus Factor".

## Objectives  
* Identify how widely the work in a project is distributed across contributors.
* Identify the key people in a project that are doing the majority of the work.

## Implementation  
*The usage and dissemination of health metrics may lead to privacy violations. Organizations may be exposed to risks. These risks may flow from compliance with the GDPR in the EU, with state law in the US, or with other law. There may also be contractual risks flowing from terms of service for data providers such as GitHub and GitLab. The usage of metrics must be examined for risk and potential data ethics problems. Please see [CHAOSS Data Ethics document](https://github.com/chaoss/community/blob/main/data-use-statement.md) for additional guidance.*

The formula for Contributor Absence Factor is a percentage calculation -50% will be our threshold-
followed by adding up each contributor's contributions sorted in decreasing order until we reach
the threshold.

If we have 8 contributors who each contribute the following number of contributions to a project: `1000, 202, 90, 33, 332, 343, 42, 433`, then we can determine the Contributor Absence Factor by first identifying the 50% of total contributions for all the contributors.

**Summary:** 50% of total contributions = `1,237.5`, so the Contributor Absence Factor is `2`.

**Full Solution:**
1. Arrange the data in descending order: `1000, 433, 343, 332, 202, 90, 42, 33`
2. Compute the 50% of the total:
   -  `(1,000 + 433 + 343 + 332 + 202 + 90 + 42 + 33) * 0.5 = 1,237.5`
3. Adding up the first two contributors in our ranking we get `1,433`.
4. **Answer**: as `1,433 > 1,237.5`, more than the 50% of contributions is performed by only `2` contributors, thus the `Contributor Absence Factor = 2`.

### Filters
* Time: The Contributor Absence Factor may be vary for different time periods. The Contributor Absence Factor over the life of a project may misrepresent the current level of contributor engagement in the project.
* Repository Group: Many open source projects include multiple repositories, and in some cases examining all of the repositories associated with any given project provides a more complete picture of the Contributor Absence Factor.

### Visualizations (optional)

![Contributor Absence Factor for CHAOSS Project in 2020](https://raw.githubusercontent.com/chaoss/wg-risk/main/focus-areas/business-risk/images/bus-factor_chaoss-2020.png)

The Contributor Absence Factor for the CHAOSS Project in 2020, when considering only git commits, was 5.

### Tools Providing the Metric
1. [Augur](https://github.com/chaoss/augur)
2. [GrimoireLab](https://chaoss.github.io/grimoirelab) provides this metric out of the box, not as a single number but as a visualization.

### Data Collection Strategies
The data collection strategy depends on the [Types of Contributions](https://chaoss.community/metric-types-of-contributions/) used for calculating the Contributor Absence Factor. Contributor Absence Factor is often calculated for commits but other types of contributions can be used for this as well, separately or combined.


## References
