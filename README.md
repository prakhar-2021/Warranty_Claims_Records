# Warranty_Claims_Records
The dataset involves typical warranty claims records.The overarching goal is to use this data to identify, analyze, and proactively address product quality and safety issues, which is core to AxionRay’s mission.This report contains the column analysis, data cleaning summary, visualizations, generated tags and key takeaways.

### Column Analysis
The dataset contains fields typical of warranty claims, such as:
- __Identification__ : *VIN, TRANSACTION ID*
- __Complaint/Repair Details__ : *CORRECTION VERBATIM, CUSTOMER VERBATIM (free text fields detailing the fix and the customer’s concern), REPAIR DATE, CAUSAL PART NM, GLOBAL LABOR CODE DESCRIPTION*
- __Vehicle/Product Information__ : *PLATFORM, BODY STYLE, ENGINE, TRANSMISSION, BUILD COUNTRY, etc.*
- __Dealer/Service Information__: *LAST KNOWN DLR NAME, REPAIRING DEALER CODE, REPAIR DLR CITY, STATE, DEALER REGION, etc.*
- __Metrics__: *REPAIR AGE, KM (mileage/kilometers at time of repair), REPORTING COST, TOTALCOST, LBRCOST (cost fields).*

### Data Cleaning Summary
The data cleaning involves regular steps of removing nulls, handling empty values, etc. __IQR method__ is used for outlier detection in KM and capping the upper bound.

### Identifying Critical Columns and Visualizations
The selection of critical columns is based on their direct relevance to identifying product quality issues, customer impact, and financial risk for the stakeholders (engineering, service, finance).
Top 5 Critical Columns:
1. __PLATFORM:__ Represents the vehicle architecture, essential for grouping engineeringresponsibility and analyzing quality across product lines.
2. __KM (Mileage):__ Measures product usage at failure, crucial for reliability engineering and warranty cost forecasting (age/usage distribution of failure).
3. __CAUSAL PART NM:__ The name of the part that caused the claim/repair. Directly points to the defective component, a primary target for engineering investigation.
4. __CUSTOMER VERBATIM:__ The raw voice of the customer. Provides the earliest, most direct insight into how the failure manifests and the customer’s experience, vital for early warning detection.
5. __TOTALCOST:__ The financial impact of the claim. Key for prioritizing which issues(combination of part/platform) warrant immediate attention from a cost-reduction perspective.

### 4 Generated tags & Key takeaways
The analysis shows that a large portion of warranty claims focuses on the Steering Wheel component, signaling a concentrated quality issue.
- __Material Degradation/Fit Tag:__ Indicates systemic quality issues with the steering wheel’s surface (peeling, stitching, bubbling) related to materials, adhesive, or manufacturing finish.
- __Heater Malfunction Tag:__ Points to defects in the heating element or the associated control module (MODULE ASM-STRG WHL HT CONT), requiring electrical and hardware investigation.
- __Component Tag Distribution:__ Confirms the overwhelming dominance of the ’Steering Wheel’ in failure data.

 Based on the analysis, the following actionable recommendations are provided:
1. __Engineering/Design Team:__
 - Urgent investigation for Steering Wheel material degradation
 - Conduct supplier audit
2. __Manufacturing/Supplier Quality Team:__
 - Implement Enhanced Quality Gates
 - Supplier Audit
3. __Finance/Warranty Management Team:__
 - Forecast high-cost exposure

