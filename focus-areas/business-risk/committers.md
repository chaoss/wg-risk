# Committers

**Question:** How robust are the contributors to a community?

## Overview

Committers measure the number of developers who have committed code changes into the project's repository. Code contributions varires from larger scale [contributors](https://github.com/chaoss/wg-common/blob/master/focus-areas/who/contributors.md) to documentation authors, individuals who open issues, or other types of contributions, depending on the management style employed by an open source project. A higher number of committers generally indicates a project's health and its likelyhood of receiving updates, support, and necessary resources in the future. This metric allows organizations to assess the risk of a project being abandoned or under-supported due to limited code contributors.
McDonald et al. (2014) point out the varying leadership styles in open-source projects can impact the number contributors. Fewer code contributors may indicate projects less open to outside contributions, or simply projects that have a small number of developers contributing to the code base. A project with a diverse group of committers may indicate a more inclusive and equitable environment, attracting and retaining contributors from various backgrounds.

## Want to Know More?

<span markdown="1"><details>

<summary>Click to read more about this metric.</summary>

### Data Collection Strategies

In an open source project every individual email address that has a commit merged into the project is a "committer" (see "known issues" in the next section). Identifying the number of unique committers during a specific time period is helpful, and the formula for doing so is simple:

`Number_of_committers = distinct_contributor_ids (during some period of time with a begin date and an end date)`. For example, I may want to know how many distinct people have committed code to a project in the past 18 months. `Committers` reveals the answer.

### Known Issues with Data Quality

*   Many contributors use more than one email, which may artificially elevate the number of total committers if these shared identities are not reconciled.
*   Several committers making small, "drive by" contributions may artificially elevate this number as well.

### Filters

*   Time: Knowing the more recent number of distinct committers may more clearly indicate the number of people engaged in a project than examining the number over a project's (repository's) lifetime.
*   Commit Size: Small commits, as measured by lines of code, could be excluded to avoid a known issue
*   Commit Count: Contributors with fewer than some minimum threshold of commits in a time period could be excluded from this number.

### Visualizations

Grimoire Lab showing committers

![Grimoire Lab committers](https://raw.githubusercontent.com/chaoss/wg-risk/main/focus-areas/business-risk/images/committers_grimoire-lab.png)

Augur maintains a table for each commit record in a repository.

![Augur Commits](https://raw.githubusercontent.com/chaoss/wg-risk/main/focus-areas/business-risk/images/committers_augur.png)

To evaluate distinct committers for a repository, the following SQL, or documented API endpoints can be used:

```sql
SELECT
    cmt_author_name,
    COUNT ( * ) AS counter
FROM
    commits
WHERE
    repo_id = 22159
GROUP BY
    cmt_author_name
ORDER BY
    counter DESC
```

This expression allows an end user to filter by commit count thresholds easily, and the number of rows returned is the "Total\_Committers" for the repository.

## References

1.  Nora McDonald, Kelly Blincoe, Eva Petakovic, and Sean Goggins. 2014. Modeling Distributed Collaboration on GitHub. Advances in Complex Systems 17(7 & 8).
2.  [Grimoire Lab](https://chaoss.biterg.io/app/kibana#/dashboard/Git)

## Additional Information

To edit this metric please [submit a Change Request here](https://github.com/chaoss/wg-risk/blob/main/focus-areas/business-risk/committers.md)

To reference this metric in software or publications please use this stable URL: <https://chaoss.community/?p=3945>

<!-- # For groupings in the knowledge base
Context tags: Contributor, Platform
Keyword tags: risk, contributors, committers, maintainers
-→ 
