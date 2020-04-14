# Average Time of Open Issues

Question: How long on average are issues kept open once they are published?

## Description
The "Average Time of Open Issues" metric is one that tracks the average time it takes for an issue to be responded to and closed. This is important as the time it takes for an issue to be closed can be a factor that determines the health of an open soruce project. More often than not, the more contributors there are to a project, the more likely that project is to receive updates, support, and resources. This metric allowed for organizations to make a better informed decision on the current or future risk a project may have to be abandoned, under-supported, or lacking resources as the time it takes for issues to be closed gives a good indication of that risk.

## Objectives
To an organization or manager deciding among open source projects to incorporate into their work force, the ability and timeliness of closing issues may be important. For larger scale projects, issues may be opened and closed at a faster rate compared to smaller scale projects. Smaller scale projects may have less issues opened, but the timeliness and ability to close issues may indicate the commitment, resources, and knowledge that projects contributors has. While larger scale projects follow this sample principle, it's easier to determine commitment, resources, and knowledge of a smaller scale project. The objective of this metric is to determine the health and risk of an open source project based off of the time it takes to close an issue, which is dependent on that projects contributors.

## Implementation
In an open source project, issues are tracked on their own page in the format of opened and closed issues. Identifying the time it takes for an issue to be closed is helpful and simple, and can be accomplished by noting the start date of an issue, and comparing it with the close date of an issue. While the specific time it took to close an issue is not explicitly present, this formula can likely be implemented into a software/project such as Augur.

### Filters
- **Time Range:** It may be important to note the average time it takes to close an issue during certain parts of a project. For example, a project that has just began should have a different average time compared to a year after its creation. Knowing the trajectory of the average time may be important in decision making.
- **Issue Size:** The size or average size of issues may determine how long it takes to complete issues and should be considered.
- **Contributor Count:** The number of contributors can determine how fast issues are completed. If a large scale project is solving issues slower than a smaller scale project, the larger scale project may be less reliable, not as committed, or be lacking resources.
- **Resolved or Not:** Knowing if an issue has been solved, pushed back, or fully removed may skew the data and mislead someone making a decision in contributing to a project.

### Tools Providing the Metric
The GitHub API can can grab issues from a repository. This API would allow for the ability to grab the open and close dates of issues created within a repository. The API documentation (specifically in regard to issues) can be found here: https://developer.github.com/v3/issues/

### Data Collection Strategies
The best way to obtain the information needed for this metric is likely through the GitHub API. The GitHub API could be used to pull the relevant data regarding the closed issues found in a repository. That data could then be populated or searched using MySQL commands or similar that would produce the results needed for this metric.

## References
Here is a reference page that goes more indepth about issues within GitHub repositories: https://help.github.com/en/github/managing-your-work-on-github/about-issues
