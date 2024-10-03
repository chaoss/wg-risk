# Libyears

**Question:** What is the age of the project’s dependencies compared to current stable releases?

## Overview
Libyears measure the cumulative age of a project’s dependencies compared to their current stable releases. A dependency’s "current stable" release refers to the version intended for general use, excluding pre-release or draft versions. Libyears help quantify the gap between the project’s dependencies and their latest stable versions. This metric can be expressed in various forms, such as:
- **Total age** across all dependencies
- **Average age** of dependencies
- **Median age** of dependencies (though median may hide issues if there is a long tail of older dependencies)

The Libyears metric helps identify dependencies that are at risk due to outdated versions. Older dependencies can introduce stability, security, and vulnerability risks, as they may have known security flaws or be less supported by their maintainers. Libyears provides a valuable filter for prioritizing which dependencies need attention for updates or further inspection.

In general, a lower Libyear value indicates that the project is more up-to-date. Tools that implement this metric also often sort dependencies by age to identify the oldest, potentially riskiest, ones.

## Want to Know More?

<span markdown="1"><details>
<summary>Click to read more about this metric.</summary>

### Data Collection Strategies
Most tools that calculate Libyears provide dependency versions and calculate the gap between current stable releases and the project’s versions. Note that some tools may include version number differences (e.g., 1.1.1 vs. 1.2.3), but since version numbering schemes vary, this metric focuses on measuring the age of dependencies based on release dates.
 * **Parameters:**
Libyears are typically calculated within the context of a particular ecosystem (e.g., JavaScript or Maven). Cross-ecosystem calculations are more complex and may require a comprehensive Software Bill of Materials (SBOM).

This metric can account for:
- **Direct dependencies** only, or include **transitive dependencies** (dependencies of dependencies). Including transitive dependencies often highlights additional risks but is not supported by all tools.
- **Current stable branches:** Only the latest stable branch of a project is typically considered current. However, older branches that are still actively supported may also be acceptable. It is important that any report clearly states the criteria used.
- **Grace periods:** By default, no grace period is included when calculating how "current" a dependency is. However, if used, it should be explicitly noted in reports.

### Filters
Libyears calculations can be filtered to offer a more focused analysis:
- **Dependency level:** Direct dependencies vs. inclusion of transitive dependencies as defined in the [Upstream Code Dependencies]((https://github.com/chaoss/wg-risk/blob/master/focus-areas/dependency-risk-assessment/upstream-code-dependencies.md) metric.
- **Cumulative Libyears:** Summing the age of all dependencies.
- **Average age:** Mean age of all dependencies.
- **Median age:** Middle value of all dependency ages (though it may mask issues due to long tails).
- **Sorted list:** Dependencies sorted by age, oldest first, to quickly identify those most at risk.

### Visualizations
This is an example of Libyear as a cumulative measure of Libyears for direct dependencies, in this case with a cumulative value of 103.78 cumulative libyears. 

![LibYear Visualization](https://raw.githubusercontent.com/chaoss/wg-risk/main/focus-areas/dependency-risk-assessment/images/libyear.png)

*Figure 1: Cumulative Libyears for a project’s direct dependencies.[Source](https://github.com/nasirhjafri/libyear)*

</details></span>

## References
1. Cox, J., Bouwers, E., van Eekelen, M., & Visser, J. (2015). Measuring Dependency Freshness in Software Systems. *Proceedings of the 37th International Conference on Software Engineering* (ICSE 2015). https://ericbouwers.github.io/papers/icse15.pdf
2. Libyear: [https://libyear.com/](https://libyear.com/)

## Contributors
- Sophia Vargas (Google)
- David A. Wheeler (Linux Foundation)
- Vinod Ahuja (University of Nebraska Omaha)
- Kate Stewart (Linux Foundation)
- Duane O’Brien
- Sean Goggins (University of Missouri / CHAOSS Project)
- Yigakpoa L. Samuel (I)

## Additional Information
- To edit this metric, please [submit a Change Request here](https://github.com/chaoss/wg-risk/blob/main/focus-areas/dependency-risk-assessment/libyear.md).  
- To reference this metric in software or publications, please use this stable URL: [https://chaoss.community/?p=3976](https://chaoss.community/?p=3976).
When implementing the Libyears metric, it is important to note:
- ***Privacy & Data Ethics:** The use of health metrics like Libyears can raise privacy concerns, especially with compliance laws like GDPR in the EU or state laws in the US. Additionally, data providers (e.g., GitHub, GitLab) may have terms of service that create contractual risks. For more information, please refer to the [CHAOSS Data Ethics document](https://chaoss.community/metric-data-ethics/).*

<!-- # For groupings in the knowledge base
 Context tags: Project Dependencies, 
 Keyword tags: Age, Dependency, Dependent, Obsolete, Release, Risk
 →
