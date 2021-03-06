--- 
date: 2012-03-30 01:30:29 +1000
title: Diff-based code inspection
tags: 
- code analysis
- coding practices
- cyclomatic complexity
- measurement
- metrics
- Uncategorized
---
Here's a totally hypothetical problem to consider:

Your team is working with a large, kinda creaky code repository. You want to measure the improvements you're making in code quality, (cyclomatic complexity etc.), but the impact you make one way or the other will not make a blip when compared to the existing code (think fractions of 1% in the must extreme cases). Not only that, the code base you work on also has other teams working on it, and you don't want to measure their changes, just your own. 

How do you measure the impact your team's changes have made to code quality (for better or worse) in a meaningful, repeatable way?

I'm thinking ... <strike>pastels</strike> differential code analysis!

Instead of measuring the difference in your code metrics from week to week, you measure the delta that your changes cause to your metrics.
