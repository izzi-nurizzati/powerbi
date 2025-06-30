# powerbi

Project Title
Employee Engagement Survey 2023

Project Description
This project analyzes employee engagement survey 2023 results - a single-year analysis that focus on detailed insights, patterns & key drivers

Tools used
1.	Excel (data transformation & data manipulation)
2.	SQL (SQL Server in SSMS)
3.	Power BI (data modeling, DAX, visualization)

Dataset
1.	EmployeeData_2023 (DataYear, EmployeeID, DivisionName, DepartmentName, Gender, Year, Month)
2.	SurveyResponse_2023 (DataYear, EmployeeID, QuestionID, LikertScore, AverageScore)
3.	SurveyQuestion_MarketScore_2023 (DataYear, QuestionID, Metric, Category, QuestionText, Theme, MarketScore)
4.	MetricMapping (Metric, MetricOrder)
5.	CategoryMapping (Metric, Category, CategoryOrder)
6.	QuestionMapping (QuestionID, QuestionText, QuestionOrder)

Database design
Star Schema, 1 Fact Table (SurveyResponse_2023) with 2 Dimension Tables (EmployeeData_2023, SurveyQuestion_MarketScore_2023)

Data model
Build relationships in Table View
From Dimension Table @ Lookup Table to Fact Table, using Collie Layout

One-to-many relationship (1:*)
1.	EmployeeData_2023[EmployeeID] → SurveyResponse[EmployeeID]
2.	SurveyQuestion_MarketScore[QuestionID] → SurveyResponse[QuestionID]
3.	MetricMapping[Metric] → SurveyQuestion_MarketScore[Metric]
4.	CategoryMapping[Category] → SurveyQuestion_MarketScore[Category]

One-to-one relationship (1:1)
1.	QuestionMapping[QuestionID] → SurveyQuestion_MarketScore[QuestionID]

Metrics
1.	Overall Engagement is 77%
2.	Total Employees Surveyed is 1,037
3.	Participation Rate is 100%
4.	Male Engagement is 78%
5.	Male Headcount is 631
6.	Female Engagement is 77%
7.	Female Headcount is 406
8.	Engagement by Division:
Business Operations & Services	
●	Channel & Retail Sales	66%
●	Client Account Management	81%
●	Client Onboarding & Activation	63%
●	Customer Experience Center	77%
●	Customer Insights & Experience	81%
●	Enterprise Sales	82%
●	Implementation & Deployment	83%
●	Logistics & Fulfillment Ops	76%
●	Sales & Revenue Operations	78%
●	Technical Support Engineering	87%
Finance & Legal	
●	Finance & Legal Services	78%
Marketing & Communications	
●	Marketing & Communications		77%
People & Culture	
●	Human Resources & Talent	82%
Product & Technology	
●	Device Engineering	84%
●	Innovation & Emerging Tech	100%
●	Product Management	74%
●	Quality Assurance & Testing	78%
●	Software Engineering	78%
●	UX/UI Design	73%
Strategy & Planning	
●	Strategy & Corporate Development	79%
