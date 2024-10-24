# Test Coverage

**Question:** How well is the code tested?

## Overview
Test coverage describes the extent to which a codebase is covered by automated tests. This metric primarily focuses on two key measurements: 
1. **Subroutine Coverage:** The percentage of subroutines (e.g., functions, methods, or routines) covered by tests. 
2. **Statement Coverage:** The percentage of code statements executed during the test suite run.

This metric only measures the coverage within a repository and excludes any libraries or external software dependencies. Both of these measures provide valuable insights into how rigorously a codebase has been tested.

Test coverage is usually tracked by testing frameworks that run automated tests against the code. It helps assess the quality of a project’s code by identifying untested portions of the codebase. Understanding test coverage allows:
- **Detection of Defects:** A lack of test coverage is often correlated with a higher probability of software defects being discovered during deployment or use.
- **Assessment of Software Engineering Practices:** Higher test coverage usually indicates more rigorous development and testing practices, while low coverage may signal less mature or less rigorous development processes.

## Want to Know More?

<span markdown="1"><details>
<summary>Click to read more about this metric.</summary>

### Data Collection Strategies

### Filters
* **Time**: Changes in test coverage over time provide evidence of project attention to maximizing overall test coverage. Specific parameters include `start date` and `end date` for the time period.
* **Code_File**: Each repository contains a number of files containing code. Filtering coverage by specific file provides a more granular view of test coverage. Some functions or statements may lead to more severe software failures than others. For example, untested code in the `fail safe` functions of a safety critical system are more important to test than `font color` function testing.
* **Programming_Language**: Most contemporary open source software repositories contain several different programming languages. The coverage percentage of each `Code_File`

### Visualizations

Statements include variable assignments, loop declarations, calls to system functions, "go to" statements, and the common `return` statement at the completion of a function or method, which may or may not include the return of a `value` or `array of values`.

![Subroutine Coverage](https://raw.githubusercontent.com/chaoss/wg-risk/main/focus-areas/code-quality/images/test-coverage_subroutine-coverage.png)
  
   *Figure 1: Subroutine Coverage which measures how many of the code's subroutines (e.g., functions, methods, routines) are tested by the suite ()*

![Statement Coverage](https://raw.githubusercontent.com/chaoss/wg-risk/main/focus-areas/code-quality/images/test-coverage_statement-coverage.png)

   *Figure 2: Statement Coverage: Measures how many code statements are executed during testing. Statements include variable assignments, loops, system calls, return statements, and more. ()*

</details></span><br>

## References
1. Andrews, J.H., Briand, L.C., Labiche, Y., & Namin, A.S. (2006). Using Mutation Analysis for Assessing and Comparing Testing Coverage Criteria. *IEEE Transactions on Software Engineering, 32*(8), 608-624. https://doi.org/10.1109/TSE.2006.83
2. Frankl, P.G., & Iakounenko, O. (1998). Further Empirical Studies of Test Effectiveness. *Proceedings of the 6th ACM SIGSOFT International Symposium on Foundations of Software Engineering*, 153-162.
3. Frankl, P.G., & Weiss, S.N. (1993). An Experimental Comparison of the Effectiveness of Branch Testing and Data Flow Testing. *IEEE Transactions on Software Engineering, 19*(8), 774-787.
4. Inozemtseva, L., & Holmes, R. (2014). Coverage is not strongly correlated with test suite effectiveness. *Proceedings of the 36th International Conference on Software Engineering - ICSE 2014*, 435-445. https://doi.org/10.1145/2568225.2568271
5. Namin, A.S., & Andrews, J.H. (2009). The influence of size and coverage on test suite effectiveness. *Proceedings of the eighteenth international symposium on Software testing and analysis - ISSTA ’09*, 57. https://doi.org/10.1145/1572272.1572280

## Contributors


## Additional Information

- To edit this metric please submit a Change Request here: https://github.com/chaoss/wg-risk/blob/main/focus-areas/code-quality/test-coverage.md

- To reference this metric in software or publications, please use this stable URL: [https://chaoss.community/?p=3957](https://chaoss.community/?p=3957)

<!-- # For groupings in the knowledge base
 Context tags: 
 Keyword tags: cd, ci, ci/cd, coverage, risk, testing
 -->
