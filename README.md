# Adopt package wrapper of Jira SDK
`net.evoja.jira-dc-adopt:net.evoja.jira.dc.adopt`

This is a wrapper of some libraries which are used in plugin development
for [Jira Server (Data Center)](https://developer.atlassian.com/server/)

Currently following libraries are included:
* [com.atlassian.jira:jira-api](https://packages.atlassian.com/maven-external/com/atlassian/jira/jira-api/)
* [com.atlassian.jira:jira-core](https://packages.atlassian.com/maven-external/com/atlassian/jira/jira-core/)


We use this package to fix some errors in Jira's packaging.
Those error occure when a Java project uses modules.

For example: some classes require `atlassian.plugins.webfragment` module,
some others require `atlassian.plugins.webfragment.api`. But these two modules have
an intersection. As a result, we get the following error:

```
module net.evoja.jira.common reads package com.atlassian.plugin.web from both
atlassian.plugins.webfragment.api and atlassian.plugins.webfragment
```

Here we take all Jira's classes and compile them to a single jar-based package.

## How to use
Add the following maven dependency to your project:

```
<dependency>
	<groupId>net.evoja.jira-dc-adopt</groupId>
	<artifactId>net.evoja.jira.dc.adopt</artifactId>
	<version>9.3.1</version>
</dependency>
```
