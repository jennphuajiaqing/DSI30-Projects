# Project 1: Standardized Test Analysis
---

### Overview:
Project 1 covers:
- Backgorund & Problem Statement
- Background
- Data Dictionary
- Summary Analysis
- Outside Research
- Conclusion & Recommendations

## Background & Problem Statement

In 2016, the College Board made significant changes to SAT test format and the College Board have also partnered with Khan Academy to provide free, world-class test prep for students around the world. Such changes were made in order to increase the participation rate of SAT. This project aims to explore the trends in SAT participation for the year of 2017-2019 and to further understand how to increase participation rate in states with low participation rate.

### Data Dictionary

| **Column**               | **Type**  | **Dataset**           | **Description**                                                                         |
|---------------------------|-----------|-----------------------|-----------------------------------------------------------------------------------------|
| **state**                 | _object_  | sat _2017_to_sat_2019 | The states in the United States of America.                                             |
| **participation_17**      | _object_  | sat_2017_to_sat_2019  | The participation rate of each state for SAT in 2017 (datatype: string).                |
| **ebrw_17**               | _integer_ | sat_2017_to_sat_2019  | The mean score for the subject 'Evidence-Based Reading and Writing' for SAT in 2017. |
| **math_17**               | _integer_ | sat_2017_to_sat_2019  | The mean score for the subject 'Math' for SAT in 2017.                               |
| **total_17**              | _integer_ | sat_2017_to_sat_2019  | The mean total score for SAT in 2017.                                                |
| **participation_rate_17** | _float_   | sat_2017_to_sat_2019  | The participation rate of each state for SAT in 2017 (datatype: float).                 |
| **participation_18**      | _object_  | sat_2017_to_sat_2019  | The participation rate of each state for SAT in 2018 (datatype: string).                |
| **ebrw_18**               | _integer_ | sat_2017_to_sat_2019  | The mean score for the subject 'Evidence-Based Reading and Writing' for SAT in 2018. |
| **math_18**               | _integer_ | sat_2017_to_sat_2019  | The mean score for the subject 'Math' for SAT in 2018.                               |
| **total_18**              | _integer_ | sat_2017_to_sat_2019  | The mean total score for SAT in 2018.                                                |
| **participation_rate_18** | _float_   | sat_2017_to_sat_2019  | The participation rate of each state for SAT in 2018 (datatype: float).                 |
| **participation_19**      | _object_  | sat_2017_to_sat_2019  | The participation rate of each state for SAT in 2019 (datatype: string).                |
| **ebrw_19**               | _integer_ | sat_2017_to_sat_2019  | The mean score for the subject 'Evidence-Based Reading and Writing' for SAT in 2019. |
| **math_19**               | _integer_ | sat_2017_to_sat_2019  | The mean score for the subject 'Math' for SAT in 2019.                               |
| **total_19**              | _integer_ | sat_2017_to_sat_2019  | The mean total score for SAT in 2019.                                                |
| **participation_rate_19** | _float_   | sat_2017_to_sat_2019  | The participation rate of each state for SAT in 2019 (datatype: float).    


### Summary Analysis
Participation rate in 2017, 2018 and 2019 range from 2%-100%. North Dakota have the worst participation rate of 2% each year. While there are a few best performing states with 100% participation rate across all 3 years. Most of the best performing state like Connecticut, Delaware and Michigan made it mandatory for all high school students to take SAT in order to graduate. Connecticut even went one step further by replacing the existing statewide exam with SAT (administered for free) due to the widespread concern that the nation's students are tested too much ([*source*](https://www.nytimes.com/2015/08/07/nyregion/connecticut-to-require-all-11th-graders-to-take-the-sat.html)). 

After the change in SAT format, many states have supported the it by making SAT mandatory. Hence, state's Colorado have a participation rate change of 89%. Despite not making SAT mandatory, South Carolina's participation rate still increased by 18% from 2017 to 2019.

But in 2019, South Carolina's mean total score fell from 1070 in 2018 to 1030 in 2019 as participation rate increased by 13% from 2018 to 2019. This shows that participation rate and mean scores are inversely related.

### Outside Research
As mentioned above, there are multiple states that made it mandatory for students to take SAT. One can get the full list of states from ([*source*](https://blog.prepscholar.com/which-states-require-the-sat)). Most of these states also made SAT free for their students.

For states that does not offer SAT for free, currently the College Board offers up to 2 SAT fee waivers for students in low-income families. One can check out the requirements and learn more on what the SAT fee waiver covers from ([*source*](https://blog.prepscholar.com/sat-fee-waiver-complete-guide)). The College Board has also partnered with Khan Academy to provide free official SAT study materials to everyone. One can understand more from ([*source*](https://www.khanacademy.org/test-prep/sat/x0a8c2e5f:about-official-sat-prep-on-khan-academy/x0a8c2e5f:overview-of-official-sat-practice/a/using-khan-academys-official-sat-practice)).


### Conclusion & Recommendations
There is significant increase in SAT participation rate after the format change in 2016. The changed in format was supported by multiple states as they made it mandatory for students to take the SAT. Some even replaced their stateside exam with SAT so as to reduce students stress from taking multiple exams. 

The following recommendations would help to increase participation rate without making it mandatory for students to take SAT:

1. I would recommend to offer 1 SAT fee waivier for all students who are in the 11th and 12th grade. This would encourage everyone to attempt the SAT at least once (and not just students from low-income families). After trying SAT test once, those who wish to retake to increase their scores would be able to understand the format of the test better. They would then be able to better prepare themselves to take the SAT again (at a cost).

2. I would also recommend the College Board to provide scholarship or study grants for the students who attained high scores on their first try (for example the top 1% of people who took the SAT each year). This would further motivate students to prepare more before attempting to take SAT which would help to increase the mean total score while increasing participation rate.

3. I would also recommend the College Board and other states to further understand South Carolina's school SAT preparation. As in 2018, despite the increase in SAT participation rate, their mean total score increased too. This observation shows that their SAT preparation was able to give students the confidence to take the SAT test. It was also able to help students attain a high score and even beat their peers and seniors who took it the year before. Therefore, other states should implement similar or same SAT preparations especially for low participating states.

**References:**

Ariel Gilreath / Staff. (2018, October 28). SAT scores Jump slightly in SC, surpass national average. GREENVILLE JOURNAL. https://greenvillejournal.com/news/sat-scores-jump-slightly-in-sc-surpass-national-average/

Connecticut to require all 11th graders to take the SAT (Published 2015). (2015, August 7). The New York Times - Breaking News, US News, World News and Videos. https://www.nytimes.com/2015/08/07/nyregion/connecticut-to-require-all-11th-graders-to-take-the-sat.html

Gumbrecht, J. (2014, March 6). Major changes coming to 2016 SAT test. CNN. https://edition.cnn.com/2014/03/05/living/sat-test-changes-schools/

Heimbach, A. (n.d.). Which states require the SAT? Complete list. Online SAT / ACT Prep Blog by PrepScholar. https://blog.prepscholar.com/which-states-require-the-sat

Safier, R. (n.d.). How you get an SAT fee waiver: Complete guide. Online SAT / ACT Prep Blog by PrepScholar. https://blog.prepscholar.com/sat-fee-waiver-complete-guide

SAT prep - Continuing education programs | University of South Carolina. (n.d.). University of South Carolina. https://sc.edu/about/offices_and_divisions/continuing_education/test_preparation/sat_prep/


Using Khan Academy's official SAT practice (article). (n.d.). Khan Academy. https://www.khanacademy.org/test-prep/sat/x0a8c2e5f:about-official-sat-prep-on-khan-academy/x0a8c2e5f:overview-of-official-sat-practice/a/using-khan-academys-official-sat-practice