## 1. Description
The total number and specific licenses declared in a software package. This can include both software and documentation source files. 

## 2. Use Cases
The total number and specific licenses declared is critical in several cases: 
1. A software package invariability carries for multiple software licenses and it is critical in the acquisition of software packages to be aware of the declared licenses for compliance reasons. Licenses Declared can provide transparency for license compliance efforts. 
2. Licenses can create conflicts such that not all obligations can be fulfilled across all licenses in a software package. Licenses Declared can provide transparency on potential license conflicts present in software packages. 


## 3. Formula
This metric is an enumeration of licenses, and the number of files with that particular license declaration. 
## 4. Sample Filter and Visualization
### Filters 
1. Time: Licenses declared in a repository can change over time as the dependencies of the repository change. One of the principle motivations for tracking license presence, aside from basic awareness, is to draw attention to any unexpected new license introduction. 
2. Declared and Undeclared: Separate enumeration of files that have license declarations and files that do not. 




## 5. Sample Implementation

## 6. Known Implementations

## 7. Test Cases (Examples)

## 8. External References (Literature)
1. https://spdx.org/
2. https://www.fossology.org 



----
```markdown
# {Name of Metric}

## 1. Description
A description of what the metric is and what it captures.
The first few sentences have to match the description in the [metrics list](../activity-metrics-list.md).

## 2. Use Cases
Provide examples of how the metric might inform different stakeholders through use cases.

## 3. Formula
A generic formula (in pseudo code) to generate the metric.

## 4. Sample Filter and Visualization
Include a Sample Filter and Visualization (screenshot) of the metric from any implementation.

## 5. Sample Implementation
An example implementation, for example a SQL or Elasticsearch query.

## 6. Known Implementations
Examples of where and how metric is used. (include links to dashboard or location where metric is visible or is talked about having been used).

## 7. Test Cases (Examples)
Sample inputs (including contexts) and expected outputs for this metric. Implementers can test their implementations against these test cases. For quantitative metrics, this could include a static repository with known metric results, or just inputs and output. For qualitative metrics, this may be more difficult.

## 8. External References (Literature)
Blog posts, websites, academic papers, or books that mention the metric.
```
