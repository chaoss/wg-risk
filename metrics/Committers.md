# Committers

[Comment on Release Candidate](https://github.com/chaoss/wg-risk/issues/16)

## 1. Description
The Committers metric is the number of individuals who have committed code to a project. This is distinct from the more broadly construed "Contributors" CHAOSS metric, speaking directly to the one specific concern that arises in the evaluation of risk by managers deciding which open source project to use.  While not necessarily true in all cases, it is generally accepted that the more contributors there are to a project, the more likely that project is to continue to receive updates, support, and necessary resources. The metric therefore allows organizations to make an informed decision as to whether the number of committers to a given project potentially poses a current or future risk that the project may be abandoned or under-supported.

## 2. Use Cases
From the point of view of managers deciding among open source projects to incorporate into their organizations, the number of committers sometimes is important.  Code contributions, specifically, can vary significantly from larger scale contributor metrics (which include documentation authors, individuals who open issues, and other types of contributions), depending on the management style employed by an open source project. McDonald et al (2014) drew attention to how different open source projects are led using an open, distributed model, while others are led following highly centralized models. Fewer code contributors may indicate projects less open to outside contribution, or simply projects that have a small number of individuals who understand and contribute to the code base.

## 3. Formula
number of committers = distinct contributor ids over a time period.

### Known Confounds
1. Many contributors use more than one email, which may artificially elevate the number of total committers if these shared identities are not reconciled.
2. Several committers making small, "drive by" contributions may artificially elevate this number as well.

## 4. Sample Filter and Visualization
1. Time: Knowing the more recent number of distinct committers may more clearly indicate the number of people engaged in a project than examining the number over a project's (repository's) lifetime.
2. Commit Size: Small commits, as measured by lines of code, could be excluded to avoid a known confound
3. Commit Count: Contributors with fewer than some minimum threshold of commits in a time period could be excluded from this number.


## 5. Sample Implementation
Augur maintains a table for each commit record in a repository, as illustrated below.
![](https://github.com/chaoss/wg-risk/blob/master/metrics/images/augur_commits.png)

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

This expression allows an end user to filter by commit count thresholds easily, and the number of rows returned is the "Total_Committers" for the repository.  Adding filters is reasonably straightforward in the API and SQL.

## 6. Known Implementations
1. [Augur](https://github.com/chaoss/augur)

## 7. Test Cases (Examples)

## 8. External References (Literature)
1. Nora McDonald, Kelly Blincoe, Eva Petakovic, and Sean Goggins. 2014. Modeling Distributed Collaboration on GitHub. Advances in Complex Systems 17(7 & 8).
