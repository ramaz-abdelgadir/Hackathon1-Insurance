# ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)


## The Health Insurance
This project analyses a health insurance dataset to uncover the key factors influencing insurance charges. Using a combination of data cleaning, exploration, and visualisation, the project delivers actionable insights through interactive dashboards and reproducible workflows.

### objectives
* Build a reliable ETL pipeline to clean and standardise the raw insurance dataset.

* Explore and analyse how demographic and lifestyle factors (age, sex, BMI, children, smoker status, region) impact insurance charges.

* Create derived variables such as age_bracket, and bmi_category, to support deeper insights.

* Test hypotheses (e.g., Do smokers pay more?, Does BMI drive costs?, Are there regional differences?).

* Develop interactive dashboards in Power BI for storytelling and exploration.


## Dataset Content

we have to Choose a dataset of reasonable size to avoid exceeding the repository's maximum size of 100Gb.
The dataset includes 1,338 records with the following columns:

age – Age of the insured individual

sex – Gender (male/female)

bmi – Body Mass Index, a measure of weight relative to height

children – Number of dependents covered by insurance

smoker – Smoking status (yes/no)

region – Geographic region of residence (northeast, northwest, southeast, southwest)

charges – Individual medical insurance charges billed


## Business Requirements

The business requires a comprehensive analysis of health insurance charges to identify the main factors driving costs and to support data-driven decision-making.

🔹 Business Needs

Understand Cost Drivers

Identify demographic and lifestyle factors (age, BMI, smoker and non smoker, region, dependents) that significantly influence insurance charges.

Segmentation of Policyholders

Group customers into categories (e.g., by smoking status, BMI category, age band, and charges band) to enable better risk profiling.

Outlier Detection

Flag unusually high or low charges and BMI values that may indicate anomalies, errors, or exceptional cases requiring review.

Interactive Dashboards

Provide visual dashboards that allow stakeholders to filter, drill down, and compare groups (e.g., smokers vs non-smokers, male vs female, regions).

Documentation & Reproducibility

Ensure that all data transformations, calculations, and insights are documented for transparency and future maintainability.

## Hypothesis and how to validate?

The project explores several hypotheses about the drivers of health insurance charges. Each hypothesis will be validated through visual analysis, and comparisons in dashboards.

Hypothesis 1: Smokers incur higher charges than non-smokers

Validation:

Compare average charges of smokers vs non-smokers using bar charts.

Visualise with boxplots to show spread and outliers.

Hypothesis 2: BMI is positively correlated with charges

Validation:

Calculate correlation coefficient between bmi and charges.

Create a scatter plot (BMI vs charges) with smoker as a color dimension to highlight differences.

Optionally fit a regression line to measure effect size.

Hypothesis 3: Older individuals have higher insurance charges

Validation:

Group policyholders by age_bracket.

Compare average charges across age bracket with column charts.

Hypothesis 4: Charges vary by region

Validation:

Use bar charts to compare average charges per region.

Map visualisation to highlight geographic variation.

Hypothesis 5: Number of dependents (children) impacts charges

Validation:

Plot column chart of charges by number of children.

Run regression analysis including children as an explanatory variable.

Compare distributions across families of different sizes.



## Project Plan



### Data Collection

Source: Kaggle “Medical Cost Personal Dataset” (insurance.csv).

Format: CSV file with 1,338 rows and 7 columns.

Stored securely in the project repository under data/raw/.

### Data Processing (ETL)

Extract: Loaded the raw CSV file into Python (pandas) and Power BI (Power Query).

### Transform:

Cleaned column names and normalised categories (e.g., M/F → male/female).

Enforced correct data types (integers, floats, categories).

Removed duplicates.

Added validation flags for age, BMI, children.

Identified and flagged outliers using the IQR method.

Engineered new features (age_band, bmi_category, charges_band).

Load Exported a cleaned dataset (insurance_clean.csv) into data/processed/ for use in dashboards and analysis.

Exploratory Data Analysis (EDA)

Visualised distributions of charges, BMI, and age.

Compared charges across key demographic groups (smokers, regions, sexes, age).

Correlation analysis between continuous variables (age, BMI, charges).

Hypothesis Testing

Tested assumptions about drivers of insurance charges.

Data Visualisation & Storytelling

Built interactive dashboards in Power BI:

Overview page with KPIs and group comparisons.

Segments page with demographic breakdowns.

Drivers page to highlight relationships (BMI, smoking, age).

Included slicers and filters for interactivity.

Designed with storytelling flow: Overview → Segments → Drivers.

Interpretation & Insights

Interpreted results in plain language for non technical audience to explain why costs differ.

Identified key insights (e.g., smokers pay ~4× more, charges rise with BMI, Southeast region has higher charges).

Prepared recommendations for stakeholders to focus on high-risk groups.

Documentation & Presentation

Created data dictionary, quality report, and README.

Documented methodology for reproducibility.

Delivered a concise presentation to showcase dashboard insights.

🔹 Data Management

Raw data kept unchanged in data/raw/ (audit trail).

Processed data stored in data/processed/.

Analysis scripts stored in src/ for reproducibility.

Reports (quality checks, EDA summaries) kept in reports/.

Dashboards saved in dashboards/ as .pbix (Power BI) .

Version control with GitHub ensured team collaboration and change tracking.


## The rationale to map the business requirements to the Data Visualisations
| **Business Requirement**                                              | **Visualisation(s)**                                                   | **Rationale**                                                                                                                                                                        |
| --------------------------------------------------------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Understand **cost drivers** (smoker, sex, region, BMI, age, children) | **Bar Charts / Column Charts** (Average charges per category)          | Bar/column charts make it easy to compare average charges across categories (e.g., smoker vs non-smoker, male vs female, by region). They highlight which groups drive higher costs. |
| Explore **distribution of charges**                                   | **Histogram / KDE Plot** (Seaborn)                                     | Distribution plots reveal skewness, spread, and the presence of heavy tails in charges, helping to categorise into low, medium, and high bands.                                      |
| Detect **outliers** in charges and BMI                                | **Box Plots** (Seaborn / Plotly)                                       | Boxplots clearly show median, quartiles, and extreme values, making it easy to identify unusual policyholders that may distort averages.                                             |
| Analyse **relationships between variables**                           | **Scatter Plots** (Charges vs BMI, Charges vs Age)                     | Scatter plots highlight correlations and trends, especially when colour-coded by smoker status. Interactive versions (Plotly) allow deeper inspection.                               |
| Provide **segmentation of policyholders**                             | **Stacked Column Charts / Treemap**                                    | Segmenting by BMI category, age band, or smoker status shows population distribution and supports risk profiling.                                                                    |
| Enable **interactive exploration**                                    | **Plotly Express Interactive Charts**, **Power BI/Tableau Dashboards** | Interactive visuals allow filtering, zooming, and drilling down by region, smoker, or age band, ensuring insights are accessible to both technical and business users.               |
| Ensure **transparent documentation**                                  | **Matplotlib Baseline Bar Charts & Seaborn Distributions**             | Using static, reproducible plots in Python ensures results can be documented in notebooks and compared with interactive dashboards for consistency.                                  |



## Analysis techniques used
List the data analysis methods used and explain limitations or alternative approaches.
How did you structure the data analysis techniques. Justify your response.
Did the data limit you, and did you use an alternative approach to meet these challenges?
How did you use generative AI tools to help with ideation, design thinking and code optimisation?

## Ethical considerations
🔹 Data Privacy
The dataset used (insurance.csv) is publicly available from Kaggle and contains synthetic data, not real patient records.

No personally identifiable information (PII) is included, so risks to individual privacy are minimal.

Compliance: Since no real personal health data was processed, regulations like GDPR is not directly applicable.

🔹 Bias and Fairness

The dataset includes demographic categories (sex, age, region, smoker and non smoker).

Risk of sampling bias: The dataset may not represent the true population distribution of health insurance customers.

Potential for interpretation bias: Conclusions (e.g., smokers pay 4× more) may oversimplify real-world scenarios where socioeconomic and healthcare access factors also play roles.

🔹 Legal Issues

Dataset is open-source under Kaggle’s license → safe to use for educational and research purposes.

No confidential insurance company data was accessed.

All code, reports, and dashboards follow open-source best practices for transparency and reproducibility.


## Dashboard Design
🔹 Dashboard Content (Blocks & Widgets)

Header

Dashboard title: “Health Insurance Charges Dashboard”

Last refresh date/time (automatically shown in Power BI if published).

KPI Block (Top Row)

Card widgets:

Total Charges (£)

Average Charge (£)

% Smokers

Average BMI

Purpose: Provide immediate “headline” numbers for decision-makers.

Comparisons Block (Middle Row)

Clustered Bar Chart: Average Charges by Smoker

Clustered Bar Chart: Average Charges by Region

Clustered Bar Chart: Average Charges by Sex

Purpose: Show how demographic and lifestyle factors impact costs.

Drivers & Distribution Block (Bottom Row)

Scatter Plot: BMI vs Charges (colour = smoker, size = age)

Box Plot (Custom Visual): Charges by Smoker (distribution and outliers)

Column Chart: Average Charges by Age Band

Purpose: Highlight relationships and underlying drivers of higher charges.

Interactivity Widgets (Sidebar / Filters)

Slicers (checkbox/dropdown):

Smoker (Yes/No)

Sex (Male/Female)

Region (Northeast, Northwest, Southeast, Southwest)

Age Band (0–17, 18–29, 30–44, 45–59, 60+)

BMI Category (Underweight, Normal, Overweight, Obese)

Outlier flag (Include/Exclude)

Purpose: Allow technical and non-technical users to explore the data dynamically.

🔹 Communicating Insights
* For Non-Technical Audiences (Executives / Judges):

* KPI cards and bar charts provide clear, instantly understandable comparisons.

* Colours (e.g., red for smokers, blue for non-smokers) reinforce group differences visually.

* Simple, plain-English titles (“Average Charge by Region (£)”) make visuals self-explanatory.

* For Technical Audiences (Analysts / Data Scientists):

* Scatter plots and box plots show variability, correlations, and outliers.

* Filters (slicers) allow deep dives by age, BMI, smoker, and region.




## Unfixed Bugs
At this stage of the project, no unfixed bugs were encountered. All implemented scripts, transformations, and dashboard features worked as expected within the scope of the dataset and chosen tools.


## Development Roadmap
What challenges did you face, and what strategies were used to overcome these challenges?
What new skills or tools do you plan to learn next based on your project experience?


## Deployment
Developed in Jupyter Notebooks and VS Code using pandas, numpy, matplotlib, seaborn, and plotly.

Scripts and notebooks stored in the project’s GitHub repository under /src and /notebooks.

Power BI (Dashboard):

The cleaned dataset (insurance_clean.csv) was imported into Power BI Desktop.

Dashboards were designed locally and saved as .pbix files under /dashboards.

Visuals include KPIs, bar charts, scatter plots, box plots, and slicers for interactive filtering.




## Main Data Analysis Libraries

The following Python libraries were used to manage, clean, and analyse the insurance dataset. Each library supported a specific stage of the workflow.

1. pandas

Purpose: Data loading, cleaning, transformation, and exploration.

2. numpy

Purpose: Numerical operations and support for statistical calculations.

3. matplotlib

Purpose: Baseline plots for averages and simple data visualisation.

4. seaborn

Purpose: Advanced statistical visualisation and distribution analysis.

5. plotly.express

Purpose: Interactive visualisation with hover, zoom, and filtering.

6. Power BI

Purpose: Data visualisation, storytelling, and interactivity.

Example Dashboards:

Overview Page: KPIs, average charges by smoker, sex, and region.

Segments Page: Charges by age bands and BMI categories.

Drivers Page: Scatter plots (BMI vs charges, colour by smoker), charges vs children.

Used slicers for filtering by smoker, sex, region, age band, BMI category.

Designed navigation flow (Overview → Segments → Drivers) to support storytelling.

Together, these libraries provided a complete toolkit for ETL, EDA, visualisation, and hypothesis testing, making the project reproducible and transparent.


## Credits
 
🔹 Content

Dataset: Kaggle — Medical Cost Personal Dataset (https://www.kaggle.com/datasets/mirichoi0218/insurance
).

Python Code References:

Official documentation for pandas
, numpy
, matplotlib
, seaborn
, plotly
, and scipy
.

Stack Overflow posts for debugging specific pandas and matplotlib issues.

Power BI:

Microsoft Learn documentation for Power BI Desktop and Power Query (M).

DAX references from DAX Guide
.

Project Documentation:

Guidance and draft structuring supported by OpenAI’s ChatGPT, used for ideation, design thinking, documentation writing, and code optimisation. All AI-generated content was reviewed and adapted to ensure accuracy, context relevance, and originality.


## Media
All images are used under their respective open-source licenses, which allow redistribution and use for educational/non-commercial purposes. E.g. ![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)




## Acknowledgements (optional)
Peers and Teammates — for collaboration, idea-sharing, and constructive feedback that improved the quality of the project.

Hackathon Organisers / College Staff — for providing the opportunity, resources, and a structured environment to work on this challenge.

Generative AI Tools (ChatGPT) — used to support ideation, code optimisation, documentation structuring, and design thinking, with all outputs carefully reviewed for accuracy and adapted to fit the project’s needs.