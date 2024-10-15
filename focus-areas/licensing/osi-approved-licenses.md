# OSI Approved Licenses

Question: What percentage of a project’s licenses are OSI approved open source licenses? 

## Description

This metric provides transparency on the open source licenses used within a project. The reason for the needed transparency is that a number of licenses are being propagated that are not, in fact, open source friendly. Open source projects may not want to include any licenses that are not OSI-approved. 

As from OSI: “Open source licenses are licenses that comply with the Open Source Definition — in brief, they allow the software to be freely used, modified, and shared. To be approved by the Open Source Initiative (also known as the OSI), a license must go through the Open Source Initiative's license review process.”

## Objectives

Identify whether a project has licenses present which do not conform to the OSI definition of open source. This transparency helps projects make conscious decisions about whether or not to include licenses that are not approved by OSI.

## Implementation
*The usage and dissemination of health metrics may lead to privacy violations. Organizations may be exposed to risks. These risks may flow from compliance with the GDPR in the EU, with state law in the US, or with other law. There may also be contractual risks flowing from terms of service for data providers such as GitHub and GitLab. The usage of metrics must be examined for risk and potential data ethics problems. Please see [CHAOSS Data Ethics document](https://github.com/chaoss/community/blob/main/data-use-statement.md) for additional guidance.*


The OSI-approved licenses can be found in the SPDX-provided [Licenses.json](https://raw.githubusercontent.com/spdx/license-list-data/master/json/licenses.json).

### Visualizations

![OSI](https://raw.githubusercontent.com/chaoss/wg-risk/main/focus-areas/licensing/images/osi-approved-licenses_visualization.png)

### Tools Providing Metric

Augur provides this metric under the Risk page for a project.

Link to API documentation: https://oss-augur.readthedocs.io/en/main/rest-api/api.html#operation/License%20Coverage%20(Repo)

### Data Collection Strategies

 - Extract list of licenses from a code base, same as in License Coverage metric.
 - Compare the list of licenses to [Licenses.json](https://raw.githubusercontent.com/spdx/license-list-data/master/json/licenses.json) and take note of how many licenses are approved by the OSI.
 - Calculate the percentage of files with an OSI approved license.

## Resources

* [OSI license page](https://opensource.org/licenses)
* [SPDX License List](https://spdx.org/licenses/)
