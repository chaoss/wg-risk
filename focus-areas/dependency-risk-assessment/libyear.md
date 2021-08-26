###This metric is a release candidate. To comment on this metric please see Issue # [118](https://github.com/chaoss/wg-risk/issues/118). Following a comment period, this metric will be included in the next regular release.

# Libyears

Question: What is the age of the project’s dependencies compared to current stable releases?

## Description
Libyears explain the age of [dependencies](https://github.com/chaoss/wg-risk/blob/master/focus-areas/dependency-risk-assessment/upstream-code-dependencies.md) upon which a project (repository, or repositories of buildable software) relies, compared to the current stable releases of those dependencies. A dependency’s “current stable” release is a release intended for general use, and does not include candidate / draft releases. Age is cumulative across all dependencies for a project, and can be ascertained in multiple ways like reporting total age, average age, and possibly median age (note that median age can hide issues if there is a long tail of ages). In general, a lower Libyear number is better. Tools should also provide a list of dependencies sorted by age to provide more insight. The concept of measuring this was proposed in “Measuring Dependency Freshness in Software Systems” by Cox et al [Cox 2015].

Note: In some cases, using an older version instead of a current version may be the wiser choice; that said, this metric provides insight to help others identify where those older versions are in use.

## Objectives
The objective of the Libyears metric is to assist in the identification of dependencies that have a higher probability of posing stability, security, and vulnerability risks to a project. A long-obsolete component is more likely to have publicly-known vulnerabilities, and is also less likely to be well-supported. It is a useful initial filter for sorting dependencies to help identify the dependencies most warranting closer examination on a project.

## Implementation
### Parameters
By default this information will be within an ecosystem (e.g., JavaScript or Maven), as that is easier to compute. This metric can be computed across multiple ecosystems, but that tends to require more information, e.g., a cross-ecosystem Software Bill of Materials (SBOM).
This information could only consider direct dependencies, or it could also include all transitive dependencies. It is more likely to reveal potential problems if transitive dependencies are included, but this is not supported by all such tools.
If a project has multiple stable/supported branches, is it acceptable to consider “current” in any branch? By default, only the most recent stable branch is considered, as typically over time the older branches receive less maintenance. An alternative (though not the default) is to also accept older versions as “current” if that older version is actively supported; reports must clearly note when this alternative is used.
Should there be a grace period when a new dependency is still considered “current”? By default, the answer is no; any particular grace period is arbitrary, and the point is to try to stay current

### Filters (optional)
Dependency level (direct only, includes transitive dependencies, etc. as defined in the [Upstream Code Dependencies]((https://github.com/chaoss/wg-risk/blob/master/focus-areas/dependency-risk-assessment/upstream-code-dependencies.md) metric. 
Cumulative Libyears as a total age.
Average age of dependencies
Median age of dependencies
Sorted list of dependencies (sorted oldest-first) so the “most risky due to age” dependencies are identified first

### Visualizations (optional)
This is an example of Libyear as a cumulative measure of Libyears for direct dependencies, in this case with a cumulative value of 103.78 cumulative libyears. 

![](./images/libyear.png)

This image is source from https://github.com/nasirhjafri/libyear   


### Tools Providing the Metric (optional)
Note that some tools can also compute differences between version ids (e.g., 1.1.1 vs. 1.2.3); this can be informative, but not all dependencies use the same version numbering approaches, so for simplicity we are focusing on measuring time.

Here is an example of some tools that implement libyersars: 
https://github.com/nasirhjafri/libyear  - for Python where a requirements.txt file is used. 
https://github.com/sesh/piprot 
https://github.com/chaoss/augur - deps_libyear_worker - For Python, and Javascript right now.
https://github.com/jaredbeck/libyear-bundler - for Ruby where Gemfile is used


### Data Collection Strategies (optional)

## References

[Cox 2015] “Measuring Dependency Freshness in Software Systems” by Joel Cox, Eric Bouwers, Marko van Eekelen, and Joost Visser, https://ericbouwers.github.io/papers/icse15.pdf  
https://libyear.com/  


## Contributors
Sophia Vargas (Google)
David A. Wheeler (Linux Foundation)
VInod Ahuja (University of Nebraska Omaha)
Kate Stewart (Linux Foundation)
Duane O’Brien
Sean Goggins (University of Missouri / CHAOSS Project)
