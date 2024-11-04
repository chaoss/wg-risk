# OSI Approved Licenses

**Question:** What percentage of a project’s licenses are OSI-approved open source licenses?

## Overview
This metric measures the percentage of licenses within a project that conform to the Open Source Initiative's (OSI) standards for open source licenses. OSI-approved licenses ensure that software can be freely used, modified, and shared in accordance with the Open Source Definition. By tracking the presence of OSI-approved licenses, projects can maintain transparency about their licensing practices and avoid including licenses that do not align with the open-source ethos.

This metric is important for ensuring compliance with open source licensing standards, protecting project integrity, and fostering trust within the open source community. It helps projects make informed decisions about licensing and prevents the inadvertent inclusion of non-open-source-friendly licenses.

## Want to Know More?

<span markdown="1"><details>
<summary>Click to read more about this metric.</summary>

### Data Collection Strategies
- Extract the list of licenses from a codebase using a method similar to the one used in the License Coverage metric.
- Compare the extracted licenses to the OSI-approved list found in the [Licenses.json](https://raw.githubusercontent.com/spdx/license-list-data/master/json/licenses.json) file provided by SPDX.
- Calculate the percentage of files within the project that use an OSI-approved license.

### Filters 
- None specified.

### Visualizations
![OSI](https://raw.githubusercontent.com/chaoss/wg-risk/main/focus-areas/licensing/images/osi-approved-licenses_visualization.png)

</details></span><br>

## References
- [OSI license page](https://opensource.org/licenses)  
- [SPDX License List](https://spdx.org/licenses/)  

## Contributors
None specified.

## Additional Information
- To edit this metric, please [submit a Change Request here](https://github.com/chaoss/wg-risk/blob/main/focus-areas/licensing/osi-approved-licenses.md).  
- To reference this metric in software or publications, please use this stable URL: [https://chaoss.community/?p=3962](https://chaoss.community/?p=3962).

<!-- # For groupings in the knowledge base
**Context tags:** open source compliance, project governance, licensing  
**Keyword tags:** OSI-approved licenses, license compliance, SPDX, open source licenses, license transparency, risk management  
-->
