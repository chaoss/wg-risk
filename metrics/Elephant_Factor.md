# Elephant Factor

Question: What is the distribution of work in the community?

_This metric is a release candidate. The 30 day comment period for this metric begins on 07/01/2020 and ends on 07/31/2020. To comment on this metric please see [Issue #291](https://github.com/chaoss/wg-diversity-inclusion/issues/291). Following the comment period, this metric will be included in the release._

## Description
The minimum number of companies whose employees perform a parameterizable definition of the total percentage of commits in a software repository is a project's 'elephant factor'. For example, one common filter is to say 50% of the commits are performed by `n companies` and that is the elephant factor. One would begin adding up to the parameterized percentage using the largest organizations making contributions, and then the next largest and so on. So, for example, a project with 8 contributing organizations who each contributed 12.5% of the commits in a project would, if the elephant factor is parameterized at 50%, have an elephant factor of "4". If one of those organizations was responsible for 50% of commits in the same scenario, then the elephant factor would be "1".

Elephant Factor provides an easy-to-consume indication of the minimum number of companies performing a certain percentage (i.e. 50%) of the work. The origin of the term "elephant factor" is not clearly delineated in the literature, though it may arise out of the general identification of software sustainability as a critical non-functional software requirements by Venters et al (2014).

## Objectives
A company evaluating open source software products might use elephant factor to compare how dependent a project is on a small set of corporate contributors. Projects with low elephant factors are intuitively more vulnerable to decisions by one enterprise cascading through any enterprise consuming that tool. The parameterized filter should reasonably be different for a project to which 1,000 organizations contribute than one to which, perhaps 10 contribute. At some volume of organizational contribution, probably something less than 1,000 organizations, elephant factor is likely not a central consideration for software acquisition because reasonable managers will judge the project not vulnerable to the decisions of a small number of actors. Such thresholds are highly contextual.

## Implementation
The formula for elephant factor is a percentage calculation -it will be our threshold-
followed by adding up each company's contributions sorted in decreasing order until we reach
the threshold.

If we have 8 organizations who each contribute the following number of commits to a project: `1000, 202, 90, 33, 332, 343, 42, 433`, then we can determine the elephant factor by first identifying the 50% of total commits for all the companies.

**Summary:** 50% of total contributions = `1,237.5`, so the elephant factor is `2`.

**Full Solution:**
1. Arrange the data in descending order: `1000, 433, 343, 332, 202, 90, 42, 33`
2. Compute the 50% of the total:
   -  `(1,000 + 433 + 343 + 332 + 202 + 90 + 42 + 33) * 0.5 = 1,237.5`
3. Adding up the first two companies in our ranking we get `1,433`.
4. **Answer**: as `1,433 > 1,237.5`, more than the 50% of contributions is performed by only `2` companies, thus we can
say the `elephant factor = 2`.

### Filters
* Time: Reasonably the Elephant Factor will change if one takes a snapshot of any prior time period, so the elephant factor over the life of a product may misrepresent the current level of organizational diversity supported by the project.
* Repository Group: Many open source projects include multiple repositories, and in some cases examining all of the repositories associated with any given project provides a more complete picture of elephant factor.

### Tools Providing the Metric
1. [Augur](https://github.com/chaoss/augur)
2. [GrimoireLab](https://chaoss.github.io/grimoirelab) provides this metric out of the box, not as a single number but as a visualization.
  - View an example on the [CHAOSS instance of Bitergia Analytics](https://chaoss.biterg.io/app/kibana#/dashboard/Git).  
  - Download and import a ready-to-go dashboard containing examples for this metric visualization from the [GrimoireLab Sigils panel collection](https://chaoss.github.io/grimoirelab-sigils/panels/git/).
  - Add a sample visualization to any GrimoreLab Kibiter dashboard following these instructions:
    * Create a new `Pie` chart
    * Select the `git` index
    * Metrics Slice Size: `Count` Aggregation
    * Buckets Splice Slices: `Terms` Aggregation, `author_org_name` Field, `metric: Count` Order By, `Descending` Order, `500` Size
  - Example screenshot: ![GrimoireLab screenshot of metric Elephant_Factor](https://github.com/chaoss/wg-risk/blob/master/metrics/images/elephant_factor-GrimoireLab.png)

## References
1. Colin C. Venters, Lydia Lau, Michael K. Griffiths, Violeta Holmes, Rupert R. Ward, Caroline Jay, Charlie E. Dibsdale, and Jie Xu. 2014. The Blind Men and the Elephant: Towards an Empirical Evaluation Framework for Software Sustainability. Journal of Open Research Software 2, 1. https://doi.org/10.5334/jors.ao
2. http://philslade.blogspot.com/2015/07/what-is-elephant-factor.html
3. https://blog.bitergia.com/2016/06/07/landing-the-new-eclipse-open-analytics-dashboard/
4. https://www.stackalytics.com/
