# Lines of Code

Question: How many lines of code are in a repository?

## 1. Description
Lines of Code counts the lines of text in the source code of a program in order to describe the size of a project. This metric can also be used to help quantify the complexity of a project and the amount of work involved in creating it, however, the lines of code metric should be used in addition to other metrics to describe these aspects of the project as they are more involved and don't necessarily correlate tot the size of the code base.

## 2. Use Cases
Contributors can use the lines of code metric to understand how their contribution have influenced the size of the project they are working on.
Project maintainers can use this metric to see how the rate of growth of a project has changed over time. More specifically, they can see if a project is growing at a healthy rate or if it's progress is beginning to dwindle and needs new ideas and additions.

## 3. Formula
The lines of code metric is a fairly simple metric as it just involves counting the number of lines in a code file that are not blank and not a comment and summing that count for each code file in the repository.


## 4. Sample Filter and Visualization

### Filters
* Time frame: Specifying a smaller time frame may describe the recent or past growth of a project in greater detail.
* File type: Seeing how many lines of code each file type contains can expose which languages are most prominent in the project.
* Lines per contributor: Can be used to help identify how a specific contributor's involvement in a project has changed over time.

### Visualizations
* General/Time frame:
<img src="https://github.com/hmassa/wg-risk/blob/master/metrics/images/lines_of_code_repo.png" width="750">

* File type breakdown:
<img src="https://github.com/hmassa/wg-risk/blob/master/metrics/images/lines_of_code_file_type.png" width="750">

* Lines per contributor:
<img src="https://github.com/hmassa/wg-risk/blob/master/metrics/images/lines_of_code_file_user.png" width="750">


## 5. Sample Implementation
FOR file IN repository {
  FOR line IN file {
    IF line is not blank or a comment
      sum += lines_of_code(file)
  }
}
return sum

## 6. Known Implementations
Examples of where and how metric is used. (include links to dashboard or location where metric is visible or is talked about having been used).

## 7. External References (Literature)
* https://confluence.atlassian.com/fisheye/about-the-lines-of-code-metric-960155778.html
