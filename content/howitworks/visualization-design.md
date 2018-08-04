+++
title = "Visualization Design"
date = "2018-07-28"
author = "iCareer Climber Team"
+++

## Salary Barchart

[Visualization](http://people.ischool.berkeley.edu/~keri.wheatley/w210_salary_bar_chart/) | [Code](https://github.com/kbelsvik/career-skills-capstone/tree/master/d3_viz/salary_bar_chart)&emsp;&emsp;Built using D3.js

This visualization allows the user to see salaries from the past 5 years for their state (or national). Salaries are grouped by any "job qualifiers" on the job titles and "no_value" indicates a job has no job qualifiers. The bars show lower quartile, upper quartile, and median. The tooltip gives additional metrics.

Next Steps - Create a visualizaion that shows jobs with decreasing/increasing demand and salaries.

<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/salary-barchart.png" width="470">


## Education Barchart

[Visualization](http://people.ischool.berkeley.edu/~keri.wheatley/w210_edu_bar_chart/) | [Code](https://github.com/kbelsvik/career-skills-capstone/tree/master/d3_viz/education_histogram)&emsp;&emsp;Built using D3.js

This visualization shows a breakdown of the education on resumes. The education is only shown if the person graduated (or ended the education) before the job start date. Each color represents a different degree subject and the size of each bar represents the number of people with that degree. The tooltip gives you those details.

Next Steps - Add identifor for STEM versus non-STEM degrees.

<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/education-barchart.png" width="470">


## Job Title Hierarchy Tree Graph

[Visualization](http://people.ischool.berkeley.edu/~keri.wheatley/w210_node_graph/) | [Code](https://github.com/kbelsvik/career-skills-capstone/tree/master/d3_viz/node_graph)&emsp;&emsp;Built using D3.js

This visualization shows the most common next step for each job. Due to data constraints, the chart only shows the most common jobs stemming from each node and not from the root node.

Next Steps - Collect more data to show mutiple steps from the root node. Add a way to identify average length of time spent in each job.

<img src="https://raw.githubusercontent.com/icareerclimber/source-code/master/content/howitworks/images_folder/hierarchy-tree-graph.png" width="470">
