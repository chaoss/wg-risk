# Upstream Code Dependencies

**Question:** What projects and libraries does my project depend on?

## Overview

Upstream Code Dependencies measures the number and types of code-based dependencies embedded within a piece of open source software. It focuses on software libraries and projects that a repository directly or indirectly relies on, excluding infrastructure dependencies like databases and operating systems. By extension, awareness of Upstream Code Dependencies enables a project to evaluate the health and sustainability of each dependency, using other CHAOSS metrics.
Upstream code dependencies helps assess the health and sustainability of a project by identifying potential risks associated with relying on external code. If a critical dependency becomes unmaintained or insecure, it can jeopardize the stability of the project. Understanding these dependencies allows project maintainers to evaluate the health of upstream components using other metrics, ensuring the overall reliability of the software. It can also help identify opportunities to support underfunded or underrepresented upstream projects, furthering community sustainability.

## Want to Know More?

<span markdown="1"><details>

<summary>Click to read more about this metric.</summary>

### Data Collection Strategies (optional)

*   [Libraries.io provides a package manager focused dependency scanner (also available through Tidelift).](https://libraries.io/rubygems/bibliothecary)

*   Upstream Code Dependency metric can be implemented by analyzing project’s dependency file or by using existing tools that examine package manager data for the languages in use (e.g., package.json for JavaScript npm, pyproject.toml / requirements.txt for Python, Gemfile / Gemfile.lock for Ruby, etc.).
    Note: C/C++ generally use system package managers. Things get more complex with multiple languages, insofar as several language specific dependency files will need to be scanned.

*   **Parameters**
    All enumerated dependencies should include the specific version(s) that are used for each dependency. Note that some systems do not support, or do not use, “version pinning” and thus do not enforce a specific version.

*   Depth of Dependency Tree
    *   Direct Dependency - first order dependencies, as declared in the source code and/or package manager configuration (e.g., requirements.txt, Gemfile, etc.)
    *   Transitive Dependency - indirect dependencies, that is, dependencies beyond first order dependencies also referred to as nested or second order dependencies. For example project A under evaluation is dependent on project B and project B is dependent on Project C. For project A, project C is a transitive dependency.
    *   Circular Dependency - dependencies where if traced eventually lead back to themselves. In systems that allow circular dependencies, we assume that a given dependency is only counted once in this case.

*   Dependency State
    *   Static Dependency - Dependency is present in all the cases.
    *   Dynamic Dependency - Dependency changes in usage and in other contexts

*   Dependency on external service like use of API

*   Execution Dependency - dependencies required to execute the software. Note that certain kinds of dependencies are typically excluded from counts, as described below. These may be one or more of the following:
    *   Build Dependency -  Code require to build a piece of software
    *   Test Dependency - Code require to test a piece of software
    *   Runtime Dependency - Code require to run a piece of software

*   Language runtime dependency detail (i.e., Python’s runtime environment)? (default no). These details are provided because of the importance of runtime dependencies for quality assurance in safety critical systems.
    *   Often which language runtime will be used is controlled by virtual environments , e.g., [venv in Python]([https://docs.python.org/3/tutorial/venv.html]\(https://docs.python.org/3/tutorial/venv.html\)) ; in Ruby you’d often use [rbenv]([[https://github.com/rbenv/rbenv]\(https://github.com/rbenv/rbenv\))  or [rvm]([https://rvm.io/]\(https://rvm.io/\)) to implement (& typically included in “Gemfile” or “Gemfile.lock” and .ruby-version)
    *   PyPi is steadily increasing its “refusal to compile incompatible libraries/dependencies” logic. It's starting to “break builds”.
    *   Unfortunately not all packaging systems have a convention for recording version information of all transitive dependencies, even within their ecosystem (it should in the long run)
    *   In some systems there are many possible runtimes that might be hard to distinguish. (E.g., there are many implementations of Common Lisp & often any of them would work.)

*   Language’s built-in libraries in count (e.g., “re” in Python)? (default no)
    *   Typically many built-in libraries are executable dependencies. However, they are typically installed “in mass” by selecting the language implementation, and are often excluded from counts to simplify analysis.
    *   Example: By default, `pip freeze` does not include these types of “included with the language” libraries/dependencies.

*   Multiple versions of the same dependency are counted independently. Some systems support multiple versions of the same dependency within a system; in such cases, they are counted separately.

**Note:** It is often important to provide information on the language implementation major and minor release version at runtime.

*   Some counts and analysis needs this information. Often language runtimes and built-in libraries are omitted (see above), and this information serves as a shorthand to provide this additional information.
*   Example: The Ruby ecosystem supports the specification of the language runtime version in Gemfiles & a .ruby-version file.
*   Example: Python releases from PyPi and Anaconda often curate different versions of libraries in different ways.

### Filters

*   Trends over time (e.g., am I depending on more or fewer projects than last year)
*   Number of versions for each dependency
*   Number of references to the same dependency

### Visualizations

![Direct Dependencies](https://raw.githubusercontent.com/chaoss/wg-risk/main/focus-areas/dependency-risk-assessment/images/upstream-code-dependencies_direct-dependencies.png)

![Transitive Dependencies](https://raw.githubusercontent.com/chaoss/wg-risk/main/focus-areas/dependency-risk-assessment/images/upstream-code-dependencies_transitive-dependencies.png)

![Circular Dependencies](https://raw.githubusercontent.com/chaoss/wg-risk/main/focus-areas/dependency-risk-assessment/images/upstream-code-dependencies_circular-dependencies.png)

</details></span><br>

## Contributors

*   Georg Link
*   Matt Germonprez
*   Sean Goggins
*   Sophia Vargas
*   Kate Stewart
*   Vinod Ahuja
*   David A. Wheeler
*   Arfon Smith
*   Elizabeth Barron
*   Ritik Malik
*   Dhruv Sachdev
*   Daune O’Brien
*   Michael Scovetta
*   Peculiar C Umeh

## Additional Information

To edit this metric please [submit a Change Request here](https://github.com/chaoss/wg-risk/blob/master/focus-areas/dependency-risk-assessment/upstream-code-dependencies.md)

To reference this metric in software or publications please use this stable URL: \[https://chaoss.community/?p=3977]\(https://chaoss.community/?p=3977)

<!-- # For groupings in the knowledge base
Context tags: Ecosystem, Software
Keyword tags: risk, dependent, dependency, upstream, reuse, reused, package, packages
-->
