# Committers

Question: How robust and diverse are the contributors to a community?

## Description
The Committers metric is the number of individuals who have committed code to a project. This is distinct from the more broadly construed ["Contributors" CHAOSS metric](https://github.com/chaoss/wg-common/blob/master/focus-areas/who/contributors.md), speaking directly to the one specific concern that arises in the evaluation of risk by managers deciding which open source project to use.  While not necessarily true in all cases, it is generally accepted that the more contributors there are to a project, the more likely that project is to continue to receive updates, support, and necessary resources. The metric therefore allows organizations to make an informed decision as to whether the number of committers to a given project potentially poses a current or future risk that the project may be abandoned or under-supported.

## Objectives

From the point of view of managers deciding among open source projects to incorporate into their organizations, the number of committers sometimes is important.  Code contributions, specifically, can vary significantly from larger scale contributor metrics (which include documentation authors, individuals who open issues, and other types of contributions), depending on the management style employed by an open source project. McDonald et al (2014) drew attention to how different open source projects are led using an open, distributed model, while others are led following highly centralized models. Fewer code contributors may indicate projects less open to outside contribution, or simply projects that have a small number of individuals who understand and contribute to the code base.

## Implementation

In an open source project every individual email address that has a commit merged into the project is a "committer" (see "known confounds" in the next section). Identifying the number of unique committers during a specific time period is helpful, and the formula for doing so is simple: 

`Number_of_committers = distinct_contributor_ids (during some period of time with a begin date and an end date)`. For example, I may want to know how many distinct people have committed code to a project in the past 18 months. `Committers` reveals the answer. 

### Known Issues with Data Quality
* Many contributors use more than one email, which may artificially elevate the number of total committers if these shared identities are not reconciled.
* Several committers making small, "drive by" contributions may artificially elevate this number as well.

### Visualizations

From Grimoire Lab showing committers

<img src="https://github.com/chaoss/wg-risk/blob/master/metrics/images/GL.Committers.png" width="750">

### Filters
* Time: Knowing the more recent number of distinct committers may more clearly indicate the number of people engaged in a project than examining the number over a project's (repository's) lifetime.
* Commit Size: Small commits, as measured by lines of code, could be excluded to avoid a known confound
* Commit Count: Contributors with fewer than some minimum threshold of commits in a time period could be excluded from this number.

## Tools Providing the Metric
Augur maintains a table for each commit record in a repository.

<img src="https://github.com/chaoss/wg-risk/blob/master/metrics/images/augur_commits.png" width="300">

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

This expression allows an end user to filter by commit count thresholds easily, and the number of rows returned is the "Total_Committers" for the repository. 

[Grimoire Lab](https://chaoss.biterg.io/app/kibana#/dashboard/Git) additionally provides insight into committers. 

## References
1. Nora McDonald, Kelly Blincoe, Eva Petakovic, and Sean Goggins. 2014. Modeling Distributed Collaboration on GitHub. Advances in Complex Systems 17(7 & 8).
