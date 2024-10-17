# Elephant Factor

**Question: What is the distribution of work in the community across companies?**

## Overview

Elephant factor measures the minimum number of companies whose employees contribute a specified percentage of the total commits in a software repository. This metric provides a quantitative indicator of the project's dependency on a small set of corporate contributors. A high elephant factor suggests that the project is heavily reliant on a few key contributors, making it more vulnerable to disruptions or changes in their involvement or a lack of diversity among contributors, as a small number of companies dominate the project. While low elephant factor indicates a more distributed contributor base, which can enhance the project's resilience and longevity or could indicate a more diverse and inclusive community. Elephant Factor provides an easy-to-consume indication of the minimum number of companies performing a certain percentage (i.e. 50%) of the work. The parameterized filter should reasonably be different for a project to which 1,000 organizations contribute than one to which, perhaps 10 contribute. The origin of the term "elephant factor" is not clearly delineated in the literature, though it may arise out of the general identification of software sustainability as a critical non-functional software requirement by Venters et al (2014).

## Want to Know More?

<span markdown="1"><details><summary>Click to read more about this metric.</summary>

*   **Elephant Factor Formula**
    The formula for elephant factor is a percentage calculation -it will be our threshold-
    followed by adding up each company's contributions sorted in decreasing order until we reach
    the threshold. If we have 8 organizations who each contribute the following number of commits to a project: `1000, 202, 90, 33, 332, 343, 42, 433`, then we can determine the elephant factor by first identifying the 50% of total commits for all the companies.

*   **Summary:** 50% of total contributions = `1,237.5`, so the elephant factor is `2`.

*   **Full Solution:**
    1.  Arrange the data in descending order: `1000, 433, 343, 332, 202, 90, 42, 33`
    2.  Compute the 50% of the total:
    *   `(1,000 + 433 + 343 + 332 + 202 + 90 + 42 + 33) * 0.5 = 1,237.5`
    3.  Adding up the first two companies in our ranking we get `1,433`.
    4.  **Answer**: as `1,433 > 1,237.5`, more than the 50% of contributions is performed by only `2` companies, thus we can
        say the `elephant factor = 2`.

### Filters

*   Time: Reasonably the Elephant Factor will change if one takes a snapshot of any prior time period, so the elephant factor over the life of a product may misrepresent the current level of organizational diversity supported by the project.
*   Repository Group: Many open source projects include multiple repositories, and in some cases examining all of the repositories associated with any given project provides a more complete picture of elephant factor.

### Visualizations

[GrimoireLab Sigils panel collection](https://chaoss.github.io/grimoirelab-sigils/panels/git/).
![GrimoireLab screenshot of metric Elephant\_Factor](https://raw.githubusercontent.com/chaoss/wg-risk/main/focus-areas/business-risk/images/elephant-factor_grimoire-lab.png)

</details></span>

## References

1.  Colin C. Venters, Lydia Lau, Michael K. Griffiths, Violeta Holmes, Rupert R. Ward, Caroline Jay, Charlie E. Dibsdale, and Jie Xu. 2014. The Blind Men and the Elephant: Towards an Empirical Evaluation Framework for Software Sustainability. Journal of Open Research Software 2, 1. https://doi.org/10.5334/jors.ao
2.  http://philslade.blogspot.com/2015/07/what-is-elephant-factor.html
3.  https://blog.bitergia.com/2016/06/07/landing-the-new-eclipse-open-analytics-dashboard/
4.  [Augur](https://github.com/chaoss/augur)
5.  [GrimoireLab](https://chaoss.github.io/grimoirelab)
6.  [CHAOSS instance of Bitergia Analytics](https://chaoss.biterg.io/app/kibana#/dashboard/Git)

## Contributors

*   Elizabeth Barron
*   Matt Germonprez
*   Kevin Lumbard
*   Yash Prakash
*   Georg Link
*   Maalik
*   Peculiar C. Umeh

## Additional Information

To edit this metric please [submit a Change Request here](https://github.com/chaoss/wg-risk/blob/main/focus-areas/business-risk/elephant-factor.md)

To reference this metric in software or publications please use this stable URL: <https://chaoss.community/?p=3940>

<!-- # For groupings in the knowledge base
Context tags: Organization, Community, Contribution
Keyword tags: risk, company dependence, contributors, committers, maintainers
→ 
