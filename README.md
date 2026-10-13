# PMO Portfolio: From Strategy to Success

A Power BI portfolio analytics project developed for **FP20 Analytics Challenge 41**. The report helps portfolio leaders review project health, identify delivery risks, prioritise interventions, and investigate opportunities to improve benefit realisation and resource utilisation.

> **Data note:** The source workbook was supplied for the challenge.

## Business objective

Project portfolios need more than a simple status report. Leaders need visibility into schedule performance, cost efficiency, resource capacity, risk exposure, and expected business benefits.

This report supports questions such as:
- Which projects need management attention?
- Where are schedule or cost performance concerns emerging?
- Which projects have high risk exposure or resource capacity gaps?
- How do forecast benefits compare with realised benefits?
- Which projects have the greatest forecast benefit relative to approved budget?
- Where should leaders investigate recovery, acceleration, resource reallocation, or formal closure?

Recommendations are decision support and should be reviewed against project context before action is taken.

Power BI Report link : https://app.powerbi.com/view?r=eyJrIjoiNDdmMjAzN2ItNGI1Yy00YTYzLWEyYTktMGMyNGMyM2YwNWZkIiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9

## Report pages

### 1. Executive Portfolio Health
Portfolio-level overview of project counts, active projects, schedule and cost performance, forecast delays, benefit trends, project status, and recommended actions.

<img width="1519" height="739" alt="image" src="https://github.com/user-attachments/assets/0fa818ea-628b-4643-9cd4-360e3fb36ce5" />


### 2. Project Prioritisation & Action
Project-level view of intervention categories, risk exposure by priority, business-unit performance, forecast delays, strategic alignment versus risk exposure, and expected value relative to approved budget.

<img width="1374" height="737" alt="image" src="https://github.com/user-attachments/assets/e336ba92-1a1b-4998-a89a-6651bf485f22" />

### 3. Benefits, Resources & Delivery Improvement
View of planned versus realised benefits, forecast cost overrun, resource capacity gaps, overdue milestones, overdue mitigation actions, SPI versus CPI, and an operational improvement watchlist.

<img width="1368" height="739" alt="image" src="https://github.com/user-attachments/assets/cd850c4b-72be-4aee-aebd-e58dc75726f4" />

## Dataset and data grain

The project uses the Excel workbook supplied for FP20 Analytics Challenge 41. The central table is `FactProjectMonthly`.

**Logical grain:** one project per reporting date, represented by `ProjectKey` and `ReportingDateKey`.

The same project can appear in multiple monthly snapshots. Snapshot-based or cumulative values—such as budgets, costs, forecast benefits, realised benefits, and progress—must be evaluated at the appropriate reporting date. Summing these values across all snapshots can double-count the same project.

## Data model

The report uses a dimensional modelling approach with:
- `FactProjectMonthly`: monthly project performance snapshots.
- `Dim_project`: project-level attributes.
- `Dim_date`: reporting calendar and time analysis.

There are other dimension table like dim_location, ,dim_businessunit, dimprogramme which are connect to FactProjectMonthly

<img width="842" height="728" alt="image" src="https://github.com/user-attachments/assets/32280b01-ed3d-4fb3-aea5-1a6cd899093b" />

The supplied workbook schema also lists keys for programme, business unit, location, delivery model, strategic theme, project manager, and sponsor. Include those dimensions in the published model only when the corresponding columns are present in the loaded query and the relationships have been validated.

Recommended modelling checks:
1. Confirm the fact-table grain and uniqueness of the project/reporting-date combination.
2. Validate key data types and relationships.
3. Use dimension-to-fact relationships only where the data supports them.
4. Verify filter direction and slicer interactions.
5. Check that latest-snapshot measures behave as intended under date and other report filters.



## Data preparation and quality checks

Document only transformations actually performed. The validation checklist includes:
- Checking data types, missing values, and duplicate records.
- Validating project and reporting-date keys.
- Reviewing date, currency, percentage, and hour fields.
- Checking benefit-to-date values before using them in realisation ratios.
- Confirming the sign convention of `ResourceCapacityGapHours`.
- Ensuring monthly snapshots are not double-counted.
- Validating measures against source rows and report filters.

## Tools
- Microsoft Power BI
- Power Query
- DAX
- Excel source workbook supplied for the challenge
- MYSQL for Adhoc Analysis




## How to explore the project

1. Read the business objective and report-page overview.
2. Review the data grain and model notes.
3. Review metric definitions and calculation cautions.
4. Open the Power BI report locally, if available and permitted.
5. Use slicers to explore project status, priority, reporting period, and project-level exceptions.
6. Validate management recommendations against the underlying project record.

## Limitations
- The analysis reflects the supplied challenge dataset and its definitions.
- Forecast values are estimates, not guaranteed outcomes.
- Associations between resource gaps and delivery slippage do not prove causation.
- A high forecast benefit-to-budget ratio does not automatically mean a project is healthy, profitable, or delivering benefits already.
- Aggregated resource gaps can net positive and negative project-level gaps against each other.
- The current report has three analytical pages. Confirm challenge page limits and required visuals before final submission.

## Author
**Amit Bahedia**  
Data & Research Professional | Microsoft Certified: PL-300 (Power BI) & DP-600 (Microsoft Fabric) | Market Intelligence and Business Insights | Excel • SQL • Power BI • Python

- LinkedIn: https://www.linkedin.com/in/amitbahedia/
- GitHub: https://github.com/amitbahedia

## Acknowledgement
Created using the dataset supplied for FP20 Analytics Challenge 41. Credit the challenge organisers and follow the dataset's terms when publishing or redistributing materials.
