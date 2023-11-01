# License Count

Question: How many different licenses are there?

## Description
The total count of identified licenses in a software package where the same license can be counted more than once if it is found in multiple source files. This can include both software and document related licenses. This metric also provides a binary indicator of whether or not the repository contains files without license declarations. This metric is a "complexity of licensing case" flag for open source managers. For example, the ideal case would look like the table below:

| Number of Licenses  | Files Without Licenses    |
| ------------- |-------------|
| 1      | FALSE |

A more common case would require references to [Licenses Declared](https://github.com/chaoss/wg-risk/blob/master/metrics/License_Declared.md) and [License Coverage](https://github.com/chaoss/wg-risk/blob/master/metrics/License_Coverage.md) metrics, in the situation reflected in this table:

| Number of Licenses  | Files Without Licenses    |
| ------------- |-------------|
| 11      | TRUE |

## Objectives
The most simple case for an IT Manager overseeing the acquisition and management of open source software or an Open Source Program Office or community manager delivering open source software to the marketplace is to have a single license type declared across all files. This metric will illustrate quickly and visibly if there is one license or more than one; and the larger the number, the more complex the considerations grow for decision makers.

The second aspect of this metric is the binary indicator of whether or not the repository (package) includes files that do not have license declarations.


## Tools Providing the Metric

 1. [Augur](https://github.com/chaoss/augur)

License count can be found on any [Augur risk page](http://augur.osshealth.io/repo/Zephyr-RTOS/zephyr/risk) under the section "Licenses Declared". The number of rows in the table is the number of licenses.

## References
1. https://spdx.org/
2. https://www.fossology.org
