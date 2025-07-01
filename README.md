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
From Dimension Table @ Lookup Table to Fact Table, using Collie Layout

One-to-many relationship (1:*)
1.	EmployeeData_2023[EmployeeID] → SurveyResponse[EmployeeID]
2.	SurveyQuestion_MarketScore[QuestionID] → SurveyResponse[QuestionID]
3.	MetricMapping[Metric] → SurveyQuestion_MarketScore[Metric]
4.	CategoryMapping[Category] → SurveyQuestion_MarketScore[Category]

One-to-one relationship (1:1)
1.	QuestionMapping[QuestionID] → SurveyQuestion_MarketScore[QuestionID]

