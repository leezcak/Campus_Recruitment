# Campus Recruitment Analysis

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Findings](#findings)
- [Recommendations](#recommendations)
- [Discussions](#discussions)
- [References](#references)


### Project Overview
This data analysis project aims to provide insights into the recruitment landscape of an university. By analysing various aspects of the recruitment profile, we seek to identify trends, seek data-driven recommendations, and gain a deper understanding of the student body.

### Data Sources
- Campus Recruitment Data: The primary dataset used for this analysis is the "campus_recruitment.csv" file, containing detailed information about placement data of an anonymous university students. The Kaggle dataset is downloadable [here](https://www.kaggle.com/datasets/benroshan/factors-affecting-campus-placement).

### Tools
- Excel: Data Cleaning & Formatting
- Tableau: Data Visualisation [[final dashboard]](https://public.tableau.com/app/profile/ireneyejinlee/viz/MBACampusRecruitmentDashboard/Dashboard1?publish=yes)

### Data Cleaning
In the initial data preparation phase, we performed the following tasks:
1. Data loading and inspection.
2. Handling duplicates and missing values.
3. Data cleaning and formatting.


### Exploratory Data Analysis
EDA involved exploring the sales data to answer key questions, such as:

- What is the distribution of gender among different degrees?
- Do secondary education affect MBA placement and starting salary?
- What is the distribution of placement status (Placed vs. Not Placed)?
- Is there correlation between MBA entrance exam grade and MBA grade?
- Is there correlation between starting salary and MBA grade?
- What is the median salary among placed students?
- How does work experience, placement status, and salary affect one another?

### Data Analysis
These are the column headers of "campus_recruitment.csv" that we renamed for better legibility.
![image](https://github.com/user-attachments/assets/cf9cca35-4f9d-4256-934e-a54d914fd1f0)
<br/><br/>

**Degree Distribution & Work Experience & Gender**
We created bar graphs to compare these variables. The steps for creating Gender Distribution in Degrees is elaborated below:
1. Drag Degree Field to Columns.
2. Drag Degree Field to Rows, change to Measure (Count).
3. Create a filter on Gender and create a Gender label.
4. Choose appropriate colour schemes to differentiate Male and Female.
<img width="1426" alt="image" src="https://github.com/user-attachments/assets/8982d92c-813a-4c9b-a300-8328f5be902c">
<br/><br/>


**Entrance Exam Grade vs. MBA Grade & Starting Salary vs. MBA Grade**
The steps for creating Starting Salary vs. MBA Grade scatterplot:
1. Drag MBA Grade to Columns.
2. Drag Starting Salary to Rows.
3. Choose colour schemes for work experience, drag Degree Field to Shape, drag Experience to label.
<img width="1420" alt="image" src="https://github.com/user-attachments/assets/bc0ab0e0-3613-4f3b-972f-c5d0ac859142">
<br/><br/>


**Placement Rates**
The steps for creating Placement Rate fields for each degree and total:
1. Create a calculated field named "Placement Rate", type in "SUM(IF [Status] = "Placed" THEN 1 ELSE 0 END)/COUNT([Status])" for calculation.
2. Drag Placement Rate to Marks->Text, filter on a degree field. Show the figure as Percentage.
3. Duplicate the worksheet for each degree.
<img width="1426" alt="image" src="https://github.com/user-attachments/assets/18be097e-014c-442b-82e8-99185d59541b"> 
<br/>
<br/>

Then format the dashboard with worksheets. The **final dashboard** is attached below.
<img width="1227" alt="Screenshot 2024-08-07 at 19 44 56" src="https://github.com/user-attachments/assets/a0a65241-a71d-43a1-867a-6fb22d3d3cd4">

### Findings
The 14-page workbook analysis results are summarised as follows:
1. The male-to-female ratio was the highest in the Science & Tech degree, then Comm&Mgmt, then others.
2. Graduates from Comm& Mgmt degrees were most likely to apply for MBA degree (145), compared to Sci&Tech (59), and Others (11).
3. Most prestigious MBA programs require at least 2 years of work experience. However, contrary to our common belief, there were twice more students who did not have prior work experience compared to whom did. There are some MBA programs that do not require work experience, and this university could be one of those programs.
4. MBA Students from Comm&Mgmt background had the highest placement rate of 70.34%, followed closely by Sci&Tech (69.49%), and then Others (45.45%). The total placement rate of this program was 68.84%.
5. Surprisingly, MBA entrance exam did not correlate with overall MBA grade, with a R-squared value of 0.05 and p-val 0.001. This could be due to the university's program management style or simply an error in data collection method.
6. The median salary was 265,000. The figure is elaborated in the Discussions section.

### Recommendations
Assuming the role of data analyst working at this university, we recommend the following actions based on our findings:
- Revise entrance exam material and data collection methods to ensure the entrance exam accurately selects high-performing individuals.
- There is a severe right skew for starting salary. Interview individuals who earn much more than average and provide support to the student body to increase their starting salary.
- Aid students who have different backgrounds from Comm&Mgmt and Sci&Tech with job applications and interview preparations to increase their placement rate.

### Discussions
There were 67 null values for Starting Salary vs. MBA Grade graph, since students who were not placed would not have a starting salary. Most of them were from Others degrees, which does not show the full picture for students from Others degrees.

One of the main challenges was identifying which country this data belongs. The median salary figure was 265,000, which is twice higher than the US MBA median salary, even for Harvard Business School. One of the outliers was even at whooping 940,000! The currency was not specified, but since this dataset is from an university in Bangalore, India, we assumed that the starting salary was in Indian Rupees. According to Indeed, the average MBA starting salary is approximately ₹357,820 per year.

The total placement rate was 68.84%, which was lower than 2023 US MBA average placement rate after 3 months - 86.8%. The placement rate varied from 100% to 44.9%, so 68.84% is on the lower end of the interval. The university could increase their placement rate by implementing our recommendations.

### References
1. [Indeed - Average MBA Salary in India](https://in.indeed.com/career-advice/pay-salary/average-mba-salary-in-india)
2. [Decimal - What is 24 lakh in numbers?](https://decimal.info/lakh/what-is-24-lakh-in-numbers.html)
3. [Fortune - MBA grads reliably earn a six-figure salary in these 6 industries](https://fortune.com/education/articles/mba-grads-reliably-earn-a-six-figure-salary-in-these-6-industries/)

