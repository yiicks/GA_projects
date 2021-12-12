# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Test Analysis

## Executive Summary

Our team of consulting interns have analysed past year data cross-state data in the United States from 2017 to 2019. This analysis takes datasets of participation rates and total/composite scores for the SAT and the ACT across states and years 2017 to 2019.

With the ACT being the main competing standardized test with high take-up rate across states, we find there are useful insights relevant to examining marketing strategies to boost SAT participation rates. **Test participation is an important profitability-linked metric because it builds College Board's student database. This in turn drives revenue generation linked to leasing such data to colleges and scholarship programs.**

**Pennsylvania, Vermont, and Virgina seem to be promising targets for College Board to double up efforts to grow participation rates.** We see them as "low hanging fruit" since 10% of 2019 potential test-takers did not take either the ACT or the SAT, and there are over 50% of 2019 test-takers already favouring the SAT. Peer group targeting may make for a good campaign strategy here.

More generally, we also believe that three-pronged strategy that includes (1) **growing** overall participation rate in states with less than 90% test participation rates, (2) **defending** existing market share, and (3) **repeating past successes** (converting states from ACT to SAT).

Also, the College Board should be aware of concerns about the progressiveness of standardized tests. Various news sources have reported that colleges are starting to drop standardized testing requirements for admissions. This is one of the reasons why California was not proposed as a state to be targeted even though it does fit into a similar category as Pennsylvaina, Vermont and Virginia based on existing participation rate trends.



## Problem Statement
***
The College Board needs advice on campaign budgeting and investments to be made towards each state in the United States.
<br>

**Tracking statewide participation, recommend which state(s) should be prioritized to boost SAT participation rates.**
***

### Contents:
- [Background](#Background)
- [Data Import & Cleaning](#Data-Import-and-Cleaning)
- [Exploratory Data Analysis](#Exploratory-Data-Analysis)
- [Data Visualization](#Visualize-the-Data)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations)


## Background

The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). They have different score ranges, which you can read more about on their websites or additional outside sources (a quick Google search will help you understand the scores for each test):
* [SAT](https://collegereadiness.collegeboard.org/sat)
* [ACT](https://www.act.org/content/act/en.html)

<b> Note: </b> <br>
Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from sudents' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude ([*source*](https://www.minotdailynews.com/news/local-news/2017/04/a-brief-history-of-the-sat-and-act/)). Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry. Lately, more and more schools are opting to drop the SAT/ACT requirement for their Fall 2021 applications ([*read more about this here*](https://www.cnn.com/2020/04/14/us/coronavirus-colleges-sat-act-test-trnd/index.html)).

> More background information is captured in later segments, especially under the "Outside Research" segment.

---

### Datasets

---
**Used datasets**: 2017-19 ACT and SAT Scores by State, which includes state participation rates (6 datasets)

* [`act_2017.csv`](./data/act_2017.csv): 2017 ACT Scores by State
* [`act_2018.csv`](./data/act_2018.csv): 2018 ACT Scores by State
* [`act_2019.csv`](./data/act_2019.csv): 2019 ACT Scores by State
* [`sat_2017.csv`](./data/sat_2017.csv): 2017 SAT Scores by State
* [`sat_2018.csv`](./data/sat_2018.csv): 2018 SAT Scores by State
* [`sat_2019.csv`](./data/sat_2019.csv): 2019 SAT Scores by State
---

### Outside Research

<font color = '#808080'> Based on your problem statement and your chosen datasets, spend some time doing outside research on state policies or additional information that might be relevant. Summarize your findings below. If you bring in any outside tables or charts, make sure you are explicit about having borrowed them. If you quote any text, make sure that it renders as being quoted. **Make sure that you cite your sources.**
</font>

**Scoring ranges per test:**
1. ACT range: 1 to 36 (composite score, from 4 compulsory sections (the writing section is optional), taken via a percentile approach against a general population; follows normal distribution <br>
<i> For more details: https://blog.prepscholar.com/what-is-a-good-act-score-a-bad-act-score-an-excellent-act-score 
    </i><br>
<br>
2. SAT range: 400 to 1600 (2 sections of range 200 to 800 each); follows normal distribution <br>
<i> For more details: https://blog.prepscholar.com/what-is-a-good-sat-score-a-bad-sat-score-an-excellent-sat-score 
    </i>

**On state requirements and related policy towards the ACT / SAT test:**
1. Standardized testing is mandatory by state policy in some states. <br>
<i> For more details: https://blog.prepscholar.com/which-states-require-the-act-full-list-and-advice
    </i><br>
    <br>
2. The College Board introduced the SAT School Day in 2010 to increase access to the SAT, although it did not gain much traction (3 states offered to juniors in 2014-15 school year). Today, however, with a revamp of the SAT assessment in 2016, we see a total of 20 states (plus Washington, DC) offering free SATs to all high school juniors in public schools. This, and point 1, impact College Board's strategy in relation to states to target.<br>
<i> For more details: https://blog.prepscholar.com/which-states-require-the-sat
    </i><br>
    <br>
3. There was a redesign of the SAT released in 2016. Whereas previously the SAT was seen as an aptitude test (rather than a knowledge test), this change made the SAT more appealing for usage as an assessment test than before.<br>
<i> For more details: https://www.theatlantic.com/education/archive/2015/06/should-the-sat-be-part-of-school/395417/
    </i><br>
    <br>
    
**Understanding the "business" of College Board**<br>

College Board's tests (PSAT, SAT exams) are "loss leaders". The profit engine is actually their student database. This is under their "College and Career Opportunities & Enrollment" division, and based on Forbes (2020; source quoted below), they generated "more than $100 million in revenue with gross margins of 41%" in 2018.

The way this works is based on an opt-in process (requested during the test, and with the option of opting in online at any time) where College Board is then given permission to share student names and some limited data with colleges and scholarship programs.

Since test participation is an opportunity to get students to opt in, and thereby add to the College Board student database, test participation rates per state per year would be reasonably linked to overall profitability at the organization at large.

<i> Source: https://www.forbes.com/sites/susanadams/2020/09/30/the-forbes-investigation-how-the-sat-failed-america/?sh=78a4e71653b5
    </i><br>
    <br>

**More about College Board:**<br>
<font color = '#606060'>
"College Board is a mission-driven not-for-profit organization that connects students to college success and opportunity. Founded in 1900, College Board was created to expand access to higher education. Today, the membership association is made up of over 6,000 of the world’s leading educational institutions and is dedicated to promoting excellence and equity in education. Each year, College Board helps more than seven million students prepare for a successful transition to college through programs and services in college readiness and college success—including the SAT, the Advanced Placement Program, and BigFuture. The organization also serves the education community through research and advocacy on behalf of students, educators, and schools." </font>
<br><br>
*The above is quoted from the College Board website. For more details: https://about.collegeboard.org/*


#### Original References

There were 10 datasets included in the [`data`](./data/) folder for this project.

* [`act_2017.csv`](./data/act_2017.csv): 2017 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`act_2018.csv`](./data/act_2018.csv): 2018 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`act_2019.csv`](./data/act_2019.csv): 2019 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))
* [`act_2019_ca.csv`](./data/act_2019_ca.csv): 2019 ACT Scores in California by School
* [`sat_2017.csv`](./data/sat_2017.csv): 2017 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2018.csv`](./data/sat_2018.csv): 2018 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))
* [`sat_2019.csv`](./data/sat_2019.csv): 2019 SAT Scores by State ([source](https://blog.prepscholar.com/average-sat-scores-by-state-most-recent))
* [`sat_2019_by_intended_college_major.csv`](./data/sat_2019_by_intended_college_major.csv): 2019 SAT Scores by Intended College Major ([source](https://reports.collegeboard.org/pdf/2019-total-group-sat-suite-assessments-annual-report.pdf))
* [`sat_2019_ca.csv`](./data/sat_2019_ca.csv): 2019 SAT Scores in California by School
* [`sat_act_by_college.csv`](./data/sat_act_by_college.csv): Ranges of Accepted ACT & SAT Student Scores by Colleges ([source](https://www.compassprep.com/college-profiles/))



### Data Dictionary


|No.|Feature|Type|Dataset|Description|Example|
|:-:|:-:|:-:|:-:|:--|:--|
|01|**state**|*string*|ACT/SAT|State names (count = 51; 50 U.S. states plus District of Columbia)|*e.g. Alabama*|
|02|**participation_act_2017**|*float*|ACT|Participation rate for ACT 2017 by State (% as decimals)| *e.g. 1.0 = 100%*|
|03|**participation_act_2018**|*float*|ACT|Participation rate for ACT 2018 by State (% as decimals)| *e.g. 1.0 = 100%*|
|04|**participation_act_2019**|*float*|ACT|Participation rate for ACT 2019 by State (% as decimals)| *e.g. 1.0 = 100%*|
|05|**participation_sat_2017**|*float*|SAT|Participation rate for SAT 2017 by State (% as decimals)| *e.g. 1.0 = 100%*|
|06|**participation_sat_2018**|*float*|SAT|Participation rate for SAT 2018 by State (% as decimals)| *e.g. 1.0 = 100%*|
|07|**participation_sat_2019**|*float*|SAT|Participation rate for SAT 2019 by State (% as decimals)| *e.g. 1.0 = 100%*|
|08|**total_act_2017**|*float*|ACT|State averages for Composite (total) score for ACT 2017 by State (1 to 36)| *e.g. 20.2*|
|09|**total_act_2018**|*float*|ACT|State averages for Composite (total) score for ACT 2018 by State (1 to 36)| *e.g. 20.2*|
|10|**total_act_2019**|*float*|ACT|State averages for Composite (total) score for ACT 2019 by State (1 to 36)| *e.g. 20.2*|
|11|**total_sat_2017**|*float*|SAT|State averages for Total score for SAT 2017 by State (400 to 1600)| *e.g. 1051*|
|12|**total_sat_2018**|*float*|SAT|State averages for Total score for SAT 2018 by State (400 to 1600)| *e.g. 1051*|
|13|**total_sat_2019**|*float*|SAT|State averages for Total score for SAT 2019 by State (400 to 1600)|*e.g. 1051*|
|14|**participation_act_2017_to_2018**|*float*|ACT|Year-on-year change (% in decimals) from 2017 to 2018 for ACT participation|*e.g. +1% change is 0.01*|
|15|**participation_act_2018_to_2019**|*float*|ACT|Year-on-year change (% in decimals) from 2018 to 2019 for ACT participation|*e.g. +1% change is 0.01*|
|16|**participation_sat_2017_to_2018**|*float*|SAT|Year-on-year change (% in decimals) from 2017 to 2018 for SAT participation|*e.g. +1% change is 0.01*|
|17|**participation_sat_2017_to_2018**|*float*|SAT|Year-on-year change (% in decimals) from 2018 to 2019 for SAT participation|*e.g. +1% change is 0.01*|



<br>

<i><font color = '#404040'>
    <b>Note</b>: While it is not explicitly written in source material, we assume state averages are referring to state means. Also, added columns from EDA included in above table. This was done later in this notebook.
    </font></i>
    

## Conclusions and Recommendations

Key insights are:
1. States where the ACT is mandatory have, in recent years, been influenced to take up the SAT.
2. Where there is already a "default" test, state participation towards that test tends to be quite sticky.
3. Pennsylvania, Vermont, and Virgina seem to be promising targets for College Board to double up efforts to grow participation rates. We see them as "low hanging fruit" since 10% of 2019 potential test-takers did not take either the ACT or the SAT, and there are over 50% of 2019 test-takers already favouring the SAT. Peer group targeting may make for a good campaign strategy here.

On top of this, the College Board should take care to make more deep dives to defend its existing market share. While there are more states now appearing to favour SATs (e.g. Colorado), the College Board must continue to maintain efforts to lobby state support so participation rates in those states are maintained.

Where there was direct capture of state support towards the SAT in states, best practices should be generated so similar efforts can be used to target other states which currently favour the ACT (15 still at 100% participation in 2019).

Also, the College Board would do well to manage concerns about the progressiveness of standardized tests. Various news sources have reported that colleges are starting to drop standardized testing requirements for admissions. This is one of the reasons why California was not proposed as a state to be targeted even though it does fit into a similar category as Pennsylvaina, Vermont and Virginia based on existing participation rate trends.
