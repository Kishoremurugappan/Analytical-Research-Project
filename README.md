📊 HR Performance Intelligence Dashboard

Department Benchmarking, Ranking & Tenure Analytics using Power BI

🔎 Project Objective

This project analyzes departmental performance and workforce tenure using advanced DAX logic and structured data modeling in Power BI.

Key Objectives:

Analyze department-wise employee performance

Benchmark department ratings against overall company performance

Rank departments using DAX-based ranking logic

Evaluate employee tenure across departments

Design an executive-ready interactive HR dashboard

📌 Purpose of HR Analytics

To enable leadership teams to track, compare, and improve departmental performance through benchmark-driven analysis and structured data modeling.

📈 Significance of Examining HR Reports

Identify high-performing and underperforming departments

Compare department ratings against company benchmarks

Understand department ranking hierarchy

Analyze employee tenure distribution

Support data-driven HR decision-making

🧠 Dashboard Capabilities

The dashboard provides:

Department Average Rating vs Company Average Rating comparison

Dynamic department ranking using RANKX

Employee service span calculation using DATEDIFF

Benchmark logic using CALCULATE + ALL to remove filter context

Interactive slicer-based department analysis

Executive-level KPI cards for quick interpretation

🏗 Data Model Architecture

The project follows a Star Schema Design.

🔹 Dimension Table

Department Desc

Department ID

Department Name

🔹 Fact Table

EmployeeData

Employee ID

Department ID

Performance Rating

Start Date

End Date

Service Span

🔹 Relationship

Department Desc (1) → EmployeeData (*)

One-to-Many Cardinality

Single Direction Filtering

Corrected auto-detected relationship configuration

🔬 Key DAX Measures
Company Average Rating
Company Average Rating =
CALCULATE(
    AVERAGE(EmployeeData[PerformanceRating]),
    ALL(EmployeeData)
)
Department Wise Rating
Department Wise Rating =
AVERAGE(EmployeeData[PerformanceRating])
Department Rank
Department Rank =
RANKX(
    ALL('Department Desc'[Department]),
    [Department Wise Rating],
    ,
    DESC,
    DENSE
)
Service Span (Calculated Column)
Service Span(Emp) =
DATEDIFF(
    EmployeeData[StartDate],
    EmployeeData[Updated End Date],
    YEAR
)
📈 Key Insights

Sales and IT departments perform above company benchmark

Finance department shows below-average performance

Higher-tenure departments demonstrate stable rating patterns

Ranking logic highlights competitive hierarchy across business units

🚧 Challenges Faced

Auto-detected relationships initially caused incorrect filter behavior

Corrected cardinality to maintain proper star schema structure

Managed filter context using CALCULATE and ALL

Resolved slicer filtering inconsistencies

Avoided many-to-many modeling complications

▶ How to Use

Download the .pbix file

Open in Power BI Desktop

Use the Department slicer to explore performance

Analyze ranking, benchmark comparison, and tenure metrics

🛠 Technical Skills Demonstrated

Star Schema Data Modeling

Relationship & Cardinality Management

Filter Context Handling

Advanced DAX:

CALCULATE

ALL

RANKX

SWITCH

SELECTEDVALUE

DATEDIFF

KPI & Benchmark Logic Design

Executive Dashboard UI Structuring

💼 Business Interpretation Skills

Translating HR performance data into actionable insights

Benchmark-based evaluation

Identifying improvement opportunities

Designing executive-level dashboards

🚀 Key Learning Outcomes

Importance of correct relationship configuration

Avoiding many-to-many modeling issues

Controlling filter propagation

Building decision-support dashboards instead of static reports

👤 Author

Kishore Murugappan
Aspiring Data Analyst | Power BI | SQL | Python

If you'd like, I can also:

🔥 Make it more recruiter-focused

🎯 Make it more technical (for hiring managers)

📊 Make it more business-impact oriented

✨ 
