# soulvibe_PowerBI
Power BI Internship Task Report
________________________________________
Objective
The objective of this internship task was to utilize Microsoft Power BI Desktop to analyze and visualize data related to educational institutions and courses offered across districts and talukas. The dataset contained details such as college names, course types, durations, aided/unaided status, and affiliations. The overall goal was to prepare a structured report with visual insights, allowing interactive exploration of course trends and institutional distribution across regions.
________________________________________
Step 1: Connecting to the Data
Actions Performed:
•	Opened Power BI Desktop.
•	Navigated to Home → Get Data → Text/CSV.
•	Selected and loaded the dataset: DA Batch 10 SQL & PowerBi Data set.csv.
•	Clicked Load to bring the data into the Power BI data model.
Analysis:
•	Verified the column structure and completeness of the data.
•	Ensured all important fields such as District, Taluka, College_Name, Course_Name, Course_Type, etc., were correctly imported.
Output:
•	The dataset was successfully loaded and ready for transformation and analysis.
________________________________________
Step 2: Data Cleaning & Preparation
Actions Performed:
•	Opened Power Query Editor via the Transform Data option.
•	Renamed columns to remove spaces and improve naming consistency (e.g., Course Name → Course_Name).
•	Replaced missing values in College_Type with "Unknown".
•	Extracted the specialization from Course_Name using Text After Delimiter (delimiter = -) and created a new column Specialization.
•	Created a new column Duration_Category using a conditional column with the following logic:
o	If Course_Duration_Months < 12 → Short
o	If 12 ≤ duration ≤ 36 → Medium
o	If > 36 → Long
Analysis:
•	Ensured the dataset was clean, well-structured, and enriched with new columns for better segmentation.
Output:
•	A clean, analysis-ready dataset with new fields: Specialization and Duration_Category.
________________________________________
Step 3: Creating Visualizations
Actions Performed:
KPI Cards:
•	Total Number of Colleges – Count Distinct of College_Name.
•	Total Unique Courses – Count Distinct of Course_Name.
•	% of Professional Courses – Created a DAX Measure:
dax
CopyEdit
ProfessionalCoursePct = 
DIVIDE(
    COUNTROWS(FILTER('DA Batch 10 SQL & PowerBi Data set', 'DA Batch 10 SQL & PowerBi Data set'[Is_Professional] = "Professional")),
    COUNTROWS('DA Batch 10 SQL & PowerBi Data set')
)
•	Average Course Duration – Average of Course_Duration_Months.
Bar Charts:
•	Number of Courses by Course_Category.
•	College Count by District.
•	Top 10 Colleges by Course Count using a Top N filter.
Pie Charts:
•	Aided vs Unaided (Aided_Unaided).
•	UG vs PG (Course_Type).
Line Chart:
•	Average Course Duration by District.
Filled Map:
•	District as Location; Count of College_Name (Distinct) as value.
Matrix:
•	University (Rows) vs Course_Type (Columns) with average of Course_Duration_Months.
Analysis:
•	Created visuals that revealed trends in educational programs across geographic and academic categories.
Output:
•	Fully visualized, data-driven dashboard containing dynamic and comprehensive insights.
________________________________________
Step 4: Adding Interactivity
Actions Performed:
•	Added slicers for the following fields:
o	Course_Category
o	College_Type
o	Course_Type
o	Prof_NonProf
•	Used Format → Edit Interactions to ensure each slicer controlled all visuals on the page.
•	Confirmed cross-filtering was properly enabled across all visuals.
Analysis:
•	Made the report flexible and user-driven by enabling filter-based visual changes.
Output:
•	Interactive dashboard allowing users to explore specific data views based on selected filters.
________________________________________
Step 5: Report Page (Q&A)
Actions Performed:
Created a new page in the Power BI report to answer specific analytical questions using visuals:
Question	Visual Type
Which district has the most colleges?	Bar chart: District vs Count of College_Name
Most common course categories?	Bar chart: Course_Category vs Count of Course_Name
Universities with widest range of course types?	Matrix: University vs Course_Type
Are unaided courses more common in professional or non-professional programs?	Stacked bar: Prof_NonProf as Axis, Aided_Unaided as Legend
College with longest average course duration?	Table: College_Name, Avg of Course_Duration_Months
Top specialization in the state?	Bar chart: Specialization, Top 1 by Course_Name count
Analysis:
•	Used grouped aggregation and filters to draw specific, business-relevant insights.
Output:
•	A clear and concise Q&A page with visual answers to key strategic questions.
________________________________________
Step 6: Finalization and Export
Actions Performed:
•	Formatted each chart with proper titles, data labels, and colors.
•	Aligned visuals for a professional layout.
•	Saved the Power BI report as .pbix file.
•	Exported report visuals as PDF and captured screenshots for documentation.
Analysis:
•	Ensured the final report was clean, understandable, and ready for stakeholders.
Output:
•	Final deliverables included a .pbix dashboard, PDF version, and screenshot-based summary.
________________________________________
Overall Conclusion
This Power BI internship task demonstrated a complete analytics pipeline — from data import and cleaning to visualization, interactivity, and reporting. The insights derived through visuals addressed strategic questions around institutional distribution, course categories, and professional offerings. The final report enables stakeholders to make informed decisions by exploring data in an interactive and visually engaging manner.

