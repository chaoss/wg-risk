# Commits

Question: How regular are commits to a community?

## Description
The Commits metric measures a project's commits over a time period and analyzes the count and regularity of them. This metric speaks
to the risk of having irregular commits to a project. This would suggest a project's contributers are either not organized on schedule, 
or that the project is being neglected. The metric therefore allows organizations see if a given project potentially poses a current or
future risk that it may be abandoned or under-supported.

## Use Cases
If a company is deciding to try to incorporate open source software into their organizations, they can use this metric to see if the
project is has a reliable contribution schedule and if it is at risk of being abandoned or under-supported. This will allow the company
to make an informed decision of whether the open source software is viable for them.

## Formula
Any open source software repository will have it's commits tracked with the timestamp that they were recieved. We can record the commits
over a time periods for visualizations:
```
number_of_commits = count(repo commits) //over a specific time period
```

## Sample Filter and Visualization
An example of this can be found on GitHub's [insights page][https://github.com/kubernetes/kubernetes/graphs/commit-activity]
- Time: Being able to filter over different time periods will let the company know both short and long term commit regularity.
- Repo: Knowing these metrics for specific repos in an organization will help them make informed decisions on whether they will
want to use the product.

## Known Implementations
[GitHub's insights page][https://github.com/kubernetes/kubernetes/graphs/commit-activity]
Examples of where and how metric is used. (include links to dashboard or location where metric is visible or is talked about having been used).

## External References (Literature)
[GitHub's insights page][https://github.com/kubernetes/kubernetes/graphs/commit-activity]
[Commit Often, Merge Often, Push Often and Relax][https://ilikekillnerds.com/2014/11/commit-often-merge-often-push-often-and-relax/]
[Commit Often, Perfect Later, Publish Once: Git Best Practices][https://sethrobertson.github.io/GitBestPractices/]

