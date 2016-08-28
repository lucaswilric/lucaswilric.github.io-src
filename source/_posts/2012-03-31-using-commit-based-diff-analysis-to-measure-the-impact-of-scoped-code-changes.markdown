---
layout: post
title: Using commit-based diff analysis to measure the impact of scoped code changes
date: 2012-03-31 16:20:52 +1000
tags: [code inspection, complexity, metrics, diff]
---

Measure change in complexity by analysing diffs
-----------------------------------------------

* Every decision removed is -1
* Every decision added is + 1
* Becomes meaningful when related to story points completed, or a similar measure
* Measures only code that has changed - i.e. the effect that WE are having as a team
* Need to tag commits or something like that, so our measurement tool knows what it should be measuring
* More relevant measurement than a whole-codebase metric, esp. when other teams work on the same codebase
* Faster to measure than a whole-codebase metric, esp. with large codebases
