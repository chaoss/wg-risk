# Core Infrastructure Initiative Best Practices Badge

Question: What is the current CII Best Practices status for the project? 

## Description

As from the [CII Best Practices Badging Page](https://bestpractices.coreinfrastructure.org/en): The Linux Foundation Core Infrastructure Initiative (CII) Best Practices badge is a way for open source projects to show that they follow best practices. Projects can voluntarily self-certify, at no cost, by using this web application to explain how they follow each best practice. Projects receive the passing badge if they meet all of the required criteria.

## Objectives

As from the [CII Best Practices Badging Page](https://bestpractices.coreinfrastructure.org/en): CII badging indicates a project’s level of compliance with “open source project best practices" as defined by the Linux Foundation's core infrastructure initiative, which focuses on CyberSecurity in open source software. The goal of the program is to encourage projects to produce better more secure software and allow others to determine if a project is following best practices.

Consumers of the badge can quickly assess which open source projects are following best practices and as a result are more likely to produce higher-quality secure software.

## Implementation

See [CII’s API documentation](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/api.md) for relevant information.

### Visualizations

![](https://i.imgur.com/mSformz.png)

### Tools Providing Metric

Augur provides an example implementation for the CII Best Practices metric.
An example of CII metrics in use can be found at http://augur.osshealth.io/repo/Zephyr-RTOS/zephyr/risk

### Data Collection Strategies

See [CII’s API documentation](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/api.md) for relevant information.

As from the [CII Best Practices Badging Page](https://bestpractices.coreinfrastructure.org/en): Projects receive the passing badge if they meet all of the required criteria. The status of each criterion, for a given project, can be 'Met', 'Unmet', 'N/A' or 'unknown'. Each criterion is in one of four categories: 'MUST', 'SHOULD', 'SUGGESTED', or 'FUTURE'. To obtain a badge, all the MUST and MUST NOT criteria must be met, all SHOULD criteria must be met OR the rationale for not implementing the criterion must be documented, and all SUGGESTED criteria have to be rated as met or unmet. Advanced badge levels of silver and gold are available if the project satisfies the additional criterion. 

## References

- CII Badging Website: https://bestpractices.coreinfrastructure.org/en 
- Augur: https://github.com/chaoss/augur



