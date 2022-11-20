# Adopt package wrapper
`net.evoja.jira-dc-adopt:net.evoja.jira.dc.adopt`

We use this package to fix some errors in Jira's packaging.

For example: some classes that we use require `atlassian.plugins.webfragment`,
some others require `atlassian.plugins.webfragment.api`. But these two packages have
an intersection. As a result, we get the following error:

```
module net.evoja.jira.common reads package com.atlassian.plugin.web from both
atlassian.plugins.webfragment.api and atlassian.plugins.webfragment
```

Here we take all Jira's classes and compile them to a single jar-based package.

