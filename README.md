
# Contact Centre Performance & Staffing Analysis
### Operations Analytics Portfolio Project | Excel Dashboard | Workforce Management

## Executive Summary

This project investigates contact centre performance across demand forecasting, workforce capacity, and customer service outcomes.

Using a simulated 30-day contact centre dataset, I analysed whether forecasted demand aligned with actual call volumes, whether staffing capacity was sufficient to meet operational requirements, and how capacity pressure coincided with customer experience deterioration.

The analysis identified a demand forecasting gap, particularly during campaign-related demand spikes, alongside staffing shortages during high-pressure periods. These operational pressures coincided with deterioration in service level, increased waiting times, and elevated call abandonment.

The findings were translated into management recommendations focused on forecast improvement, staffing alignment, intraday intervention, and proactive operational monitoring.

> **Core business question:** How can a contact centre anticipate demand, align staffing capacity, and protect customer experience during periods of operational pressure?

---

## Project Overview

| Attribute | Details |
|---|---|
| Project | Contact Centre Performance & Staffing Analysis |
| Industry | Customer Operations / Contact Centre |
| Company | Northstar CX (fictional) |
| Period analysed | October 2026 |
| Dataset | Synthetic operational data |
| Analysis tools | Microsoft Excel |
| Project type | Operations Analytics / Workforce Management |
| Deliverable | Executive performance dashboard and analytical recommendations |

---

## Business Problem

Contact centres must balance incoming demand with available staffing to maintain service quality, manage customer waiting times, and reduce abandonment.

Forecast inaccuracies can create planning challenges. When actual demand exceeds forecast, staffing plans may not adequately account for workload. If staffing capacity is insufficient, customers may experience longer waiting times, reduced service levels, and a higher likelihood of abandoning calls.

This analysis investigates four areas:

1. **Demand:** How accurately was call volume forecasted?
2. **Capacity:** Was staffing sufficient to meet workload requirements?
3. **Customer Experience:** What happened to service level, waiting times, and abandonment during operational pressure?
4. **Intraday Operations:** When did pressure occur, and what interventions could have been considered?

---

## Executive Dashboard Preview

[Executive Dashboard](./NorthstarDashboard.png)

[Download the Excel Dashboard](./NorthstarcontactCenter_Portfolio_Data.xlsx)

---
## Dataset

The project uses a simulated contact centre dataset created for analytical and portfolio purposes. It does not contain real customer, employee, or company data.

### Dataset scope

- 30 days of operational activity
- 2,880 15-minute intervals
- Approximately 75 agents
- Approximately 2,250 agent-day records
- Multiple demand scenarios

### Workbook structure

| Worksheet | Description |
|---|---|
| `Interval_15min` | Interval-level demand, forecast, staffing, and service metrics |

### Demand scenarios

| Scenario | Description |
|---|---|
| Normal | Regular operating conditions |
| Campaign | Increased demand associated with campaign activity |
| Demand Spike | Significant demand surge requiring closer capacity monitoring |

---

## Analytical Approach

The analysis was conducted through a structured process.

### 1. Data validation

Reviewed the dataset structure, completeness, consistency, and operational logic.

Validation checks included:

- Missing data
- Duplicate records
- Interval consistency
- Call volume reconciliation
- Relationships between answered, abandoned, and total calls
- Staffing metric interpretation
- KPI calculation logic

### 2. Forecast performance

Compared forecast calls against actual calls to quantify forecasting accuracy and identify where forecasting performance deteriorated.

### 3. Staffing and capacity

Compared required staffing, scheduled staffing net of shrinkage, and actual available agents to identify capacity shortfalls.

### 4. Customer experience

Investigated service level, average speed of answer, and abandoned calls to assess customer impact during different operating scenarios.

### 5. Intraday investigation

Examined the campaign demand spike at 15-minute intervals to identify periods when demand exceeded forecast and available agents fell below staffing requirements.

### 6. Management recommendations

Translated analytical findings into operational actions and monitoring recommendations.

---

# Analysis & Findings

## 1. Demand Forecasting Performance

### Objective

Determine whether the contact centre forecast accurately anticipated incoming call volumes and identify scenarios with significant forecasting errors.

### Overall results

| Metric | Result |
|---|---|
| Forecast Calls | 62,192 |
| Actual Calls | 62,850 |
| Net Forecast Error | +658 calls |
| Forecast Bias | Approximately +1.0% underforecast |
| Absolute Forecast Error | 9,825 calls |
| WAPE | Approximately 15.6% |
| Average Absolute Error per 15-minute interval | Approximately 3.4 calls |

**Interpretation**

The business underforecast total demand by 658 calls over the reporting period. However, the relatively small net difference between forecast and actual demand masks larger interval-level forecast misses.

The total absolute error of 9,825 calls indicates that forecast inaccuracies were more substantial than the net total alone suggests. Underforecasting in some intervals and overforecasting in others can offset each other when viewed only at the aggregate level.

### Forecasting formulas

**Forecast Error**

Actual Calls − Forecast Calls

- Positive value: Underforecast
- Negative value: Overforecast
- Zero: Forecast matched actual demand

**Absolute Forecast Error**

Absolute value of Forecast Error

**WAPE (Weighted Absolute Percentage Error)**

Sum of Absolute Forecast Errors ÷ Sum of Actual Calls

**Forecast Bias**

Sum of Forecast Errors ÷ Sum of Actual Calls

Positive bias indicates underforecasting; negative bias indicates overforecasting.

### Scenario analysis

The campaign demand spike was the most significant forecasting concern identified.

| Scenario | Forecast Bias | WAPE |
|---|---:|---:|
| Normal | Approximately +1% | Approximately 15% |
| Campaign | Approximately +4% | Approximately 15% |
|Demand Spike | Approximately +35% | Approximately 35% |

The Demand Spike scenario showed substantial underforecasting, suggesting the forecasting approach did not adequately capture the magnitude of demand during the spike.

### Key finding

Forecasting performance was materially weaker during demand spikes. 

### Recommendation

- Introduce demand spike-aware forecasting assumptions.
- Review historical campaign performance when forecasting future events.
- Monitor WAPE and forecast bias by scenario, day, and interval.
- Establish demand escalation triggers when actual calls materially exceed forecast.
- Review forecast accuracy after each campaign to improve future planning.

---

## 2. Staffing & Capacity Analysis

### Objective

Determine whether workforce capacity was sufficient to meet operational staffing requirements and identify periods of staffing deficit.

### Scenario staffing results

| Scenario | Required Agents | Available Agents | Net Scheduled Agents |
|---|---:|---:|---:|
| Demand Spike | 29 | 20 | 21 |
| Campaign | 14 | 13 | 14 |
| Normal | 13 | 13 | 13 |

*Figures represent reported scenario averages and should be interpreted in the context of the underlying interval calculations.*

### Demand Spike

| Staffing Metric | Agents |
|---|---:|
| Required | 29 |
| Scheduled Net of Shrinkage | 21 |
| Actual Available | 20 |
| Gap vs Requirement (Actual Availability) | 9 |
| Gap vs Requirement (Net Scheduled) | 8 |

During the demand spike, actual available staffing was approximately nine agents below the reported requirement.

This represents approximately 31% of the required staffing capacity.

The gap between net scheduled staffing and actual available staffing also indicates a further one-agent difference on average.

### Campaign

Campaign periods showed a smaller but still relevant staffing shortfall:

- Required agents: 14
- Available agents: 13
- Average shortfall: 1 agent

### Normal

Normal periods showed average required and available staffing aligned at approximately 13 agents.

However, averages can conceal interval-level staffing imbalances and do not necessarily indicate that every interval was adequately staffed.

### Key finding

Staffing capacity was most constrained during Campaign Demand Spike periods. Average staffing levels during normal operating conditions masked the larger capacity gap experienced during peak demand.

### Recommendation

- Validate the staffing requirement calculation and underlying assumptions.
- Align campaign staffing plans with anticipated demand.
- Review shrinkage assumptions and actual availability.
- Evaluate appropriate capacity buffers based on workload variability.
- Monitor required, scheduled net, and actual available staffing together.
- Develop contingency plans for periods where actual availability falls below requirements.

---

## 3. Customer Experience Analysis

### Objective

Assess whether operational pressure coincided with customer service deterioration.

The analysis reviewed:

- Service Level
- Average Speed of Answer (ASA)
- Abandoned Calls
- Abandonment Rate

### Scenario results

| Metric | Demand Spike | Campaign | Normal |
|---|---:|---:|---:|
| Average Service Level | 6.33% | 61.88% | 60.81% |
| Average ASA | 931.76 sec | 217.84 sec | 208.00 sec |
| Actual Calls | 887 | 8,428 | 53,535 |
| Abandoned Calls | 323 | 1,278 | 8,939 |
| Abandonment Rate | 36.42% | 15.16% | 16.70% |

### Customer impact during Campaign Demand Spike

Demand Spike periods exhibited:

- A significant deterioration in reported service level
- A substantial increase in average waiting time
- Elevated call abandonment
- A pronounced gap between staffing requirement and actual availability

### Abandonment Rate Calculation

Abandonment Rate = Abandoned Calls ÷ Actual Calls

| Scenario | Calculation | Abandonment |
|---|---|---:|
| Campaign Demand Spike | 323 ÷ 887 | 36.42% |
| Campaign | 1,278 ÷ 8,428 | 15.16% |
| Normal | 8,939 ÷ 53,535 | 16.70% |

### Key finding

Demand Spike periods coincided with substantially poorer customer service outcomes, including elevated waiting times and abandonment.

The findings support an operational relationship between capacity pressure and customer experience deterioration. They do not, by themselves, establish that forecast error or staffing shortages were the sole cause of the service deterioration.

### Recommendation

- Establish proactive service-level monitoring.
- Use ASA and abandonment as additional indicators of customer pressure.
- Introduce trigger-based escalation when service deteriorates.
- Consider operational interventions such as redeployment, overtime, flexible staffing, or prioritization where operationally appropriate.
- Review service performance after high-demand events.

---

## 4. Intraday Operational Investigation

### Objective

Investigate the timing of demand pressure and identify intervals requiring real-time operational intervention.

The Campaign Demand Spike scenario was examined at 15-minute intervals, focusing on the period where demand and staffing pressure were most pronounced.

### Intraday variables reviewed

- Actual Calls
- Forecast Calls
- Actual Required Agents
- Actual Available Agents
- Service Level

### Observations

During the spike:

- Actual call demand exceeded forecast in key intervals.
- Actual available staffing was below calculated staffing requirements.
- Service level deteriorated significantly during the pressure period.
- The service disruption was not uniform across the entire period.

The intraday investigation demonstrated the importance of analysing operational performance at interval level rather than relying only on daily averages.

### Key finding

A high-level daily view can conceal short periods of severe operational pressure. Intraday monitoring is necessary to identify emerging capacity problems and respond before customer outcomes deteriorate further.

### Recommendation

Implement trigger-based real-time monitoring, for example:

- Actual demand materially exceeding forecast
- Available agents falling below required agents
- Service level declining beyond an agreed threshold
- ASA increasing sharply
- Abandonment accelerating

Escalation thresholds should be agreed with Operations and Workforce Management and calibrated using historical performance.

---

# Executive Summary of Findings

| Area | Finding | Business Implication |
|---|---|---|
| Forecasting | Significant underforecasting during demand spikes | Forecasts may not adequately support campaign staffing plans |
| Staffing | Available agents materially below requirements during spike | Reduced capacity to absorb incoming workload |
| Customer Experience | Higher ASA, low Service Level, elevated abandonment during spike | Increased customer waiting and risk of lost contacts |
| Intraday Operations | Pressure concentrated in specific intervals | Daily averages can conceal severe operational disruption |

---

# Management Recommendations

## 1. Improve Campaign Forecasting

**Owner:** Forecasting / Workforce Management

- Use campaign-specific historical demand patterns.
- Review forecast bias and WAPE by scenario.
- Develop forecast adjustment processes for campaign events.
- Create escalation triggers for unexpected demand variance.

**Expected outcome:** Better anticipation of demand and improved workforce planning inputs.

## 2. Strengthen Capacity Planning

**Owner:** Workforce Planning / Scheduling

- Reassess staffing requirements against demand and workload assumptions.
- Review shrinkage and actual availability.
- Plan campaign staffing in advance.
- Evaluate evidence-based capacity buffers.
- Review schedule flexibility during high-demand periods.

**Expected outcome:** Better alignment between staffing capacity and operational requirements.

## 3. Introduce Proactive Intraday Management

**Owner:** Real-Time Management / Operations

- Monitor demand against forecast.
- Monitor required staffing against available agents.
- Establish escalation thresholds.
- Develop contingency actions for unexpected demand surges.

**Expected outcome:** Earlier identification and response to operational risk.

## 4. Protect Customer Experience

**Owner:** Operations / Customer Experience

- Monitor Service Level, ASA, and abandonment together.
- Identify intervals of severe service deterioration.
- Prioritize operational interventions during peak pressure.
- Conduct post-event reviews.

**Expected outcome:** Improved ability to protect service performance and reduce customer waiting and abandonment.

---

# Dashboard Design

The Excel dashboard was designed to present the analysis at executive level.

The objective was to communicate operational performance quickly and clearly, allowing management to identify key risks without reviewing raw interval-level data.

### Dashboard components

- Actual Calls
- Forecast WAPE
- Staffing Gap
- Abandonment Rate
- Forecast vs Actual Calls trend
- Staffing Requirement vs Scheduled Net vs Actual Available
- Customer Experience trends


---

# Tools & Skills Demonstrated

### Excel

- Data validation and reconciliation
- PivotTables
- PivotCharts
- KPI calculations
- Forecast error analysis
- WAPE and forecast bias
- Abandonment rate calculation
- Dashboard design and layout
- Data visualization

### Operations Analytics

- Demand analysis
- Workforce capacity analysis
- Staffing gap analysis
- Service level analysis
- ASA and abandonment analysis
- Intraday performance investigation
- Operational root-cause investigation
- Translating data into recommendations

### Workforce Management

- Forecast vs actual demand
- Required vs available staffing
- Shrinkage considerations
- Campaign capacity planning
- Intraday monitoring
- Real-time escalation concepts

---

# Limitations & Considerations

- The dataset is synthetic and created for demonstration purposes.
- The analysis does not represent the confidential performance of a real company.
- Scenario averages may conceal interval-level variability.

---

# Conclusion

This project demonstrates how operational data can be used to move beyond reporting metrics and investigate the underlying relationship between demand, staffing capacity, and customer experience.

The analysis identified a significant forecasting weakness during demand spike periods, a corresponding capacity gap, and customer experience deterioration during periods of operational pressure.

The most important takeaway is that contact centre performance should not be assessed using isolated KPIs. Forecast accuracy, staffing capacity, and customer service outcomes must be analysed together to identify operational risk, understand its implications, and support better decision-making.


---

*Portfolio project developed using simulated contact centre data for analytical and learning purposes.*
