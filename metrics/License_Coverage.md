# License Coverage

Question: How much of the code base has declared licenses?

## Description
How much of the code base has declared licenses. This includes both software and documentation source files and is represented as a percentage of total coverage.

## Objectives
License Coverage provides insight into the percentage of files in a software package that have a declared license, leading to two use cases:
1. A software package is sourced for internal organizational use and declared license coverage can highlight points of interest or concern when using that software package.
2. Further, a software package is provided to external, downstream projects and declared license coverage can make transparent license information needed for downstream integration, deployment, and use.

## Implementation

Data can be pulled from DoSOCSv2 and filtered through Jinja2 to get the desired information. Here is a sample of Jinja code to filter DoSOCSv2 code. The file that this implementation is inserted into may be found here:
https://github.com/DoSOCSv2/DoSOCSv2/blob/master/dosocs2/templates/2.0.tag
The code may be added to the end of the document. Run a “dosocs2 oneshot” scan and the new data will be at the end of the document. More information on DoSOCSv2 is found here:
https://github.com/DoSOCSv2/DoSOCSv2

```
{% set cnt = [0] %}
{% for file in package.files %}
{% if file.license_info[0].short_name != None %}
{% if cnt.append(cnt.pop() + 1) %}{% endif %}
{% endif %}
{% if loop.index == loop.length %}
TotalFiles: {{ loop.index }}
DeclaredLicenseFiles: {{ cnt[0] }}
PercentTotalLicenseCoverage: {{ '%0.2f' %  ((cnt[0] / loop.index) * 100) | float }}%
 {% endif %}
{% endfor %}
```

### Filters
Time: Licenses declared in a repository can change over time as the dependencies of the repository change. One of the principle motivations for tracking license presence, aside from basic awareness, is to draw attention to any unexpected new license introduction.

"Open Source Metric": Percentage of licenses on the list of Open Source Initiative (OSI) approved licenses over all found licenses. 

### Visualizations 

#### Web Presentation of DoSOCS2 Output:
![](https://i.imgur.com/HGG24bk.jpg)

#### JSON Presentation of DoSOCS2 Output:
![](https://i.imgur.com/Xyxm3q3.jpg)

### Tools Providng the Metric
* [Augur](https://github.com/chaoss/augur)

## Resources
* https://spdx.org/
  * JSON of SPDX license list: https://raw.githubusercontent.com/spdx/license-list-data/master/json/licenses.json
* https://www.fossology.org
