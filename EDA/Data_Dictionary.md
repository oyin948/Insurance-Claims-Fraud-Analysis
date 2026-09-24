# Data Dictionary — Insurance Claims Fraud Analysis

Full column reference for `Data/insurance_claims.xlsx`. See the main [README](../README.md) for analysis and findings.

| Column | Description |
| --- | ---: |
| months_as_customer, age | How long the person has been a customer, and their age |
| policy_number, policy_bind_date | Policy identifier and the date it was issued |
| policy_state, policy_csl | State where the policy was issued (IL, IN, OH) and combined single limit (e.g. 100/300) |
| policy_deductable, policy_annual_premium | Deductible amount ($500 / $1,000 / $2,000) and annual premium |
| umbrella_limit, insured_zip | Additional liability coverage limit and insured's zip code |
| insured_sex, insured_education_level | Insured's sex and education level |
| insured_occupation, insured_hobbies | Insured's occupation and stated hobby |
| insured_relationship | Insured's relationship status (husband, wife, own-child, etc.) |
| capital-gains, capital-loss | Insured's reported capital gains and losses |
| incident_date, incident_type | Date of the incident and its type (Single Vehicle Collision, Multi-vehicle Collision, Parked Car, Vehicle Theft) |
| collision_type, incident_severity | Type of collision (Front/Rear/Side/Unknown) and damage severity (Trivial/Minor/Major Damage, Total Loss) |
| authorities_contacted | Authority contacted after the incident (Police, Fire, Ambulance, Other, None) |
| incident_state, incident_city, incident_location | Where the incident occurred |
| incident_hour_of_the_day | Hour of day the incident occurred (0–23) |
| number_of_vehicles_involved | Number of vehicles involved in the incident |
| property_damage, bodily_injuries, witnesses | Whether property damage occurred, number of injuries, number of witnesses |
| police_report_available | Whether a police report is available |
| total_claim_amount, injury_claim, property_claim, vehicle_claim | Claim amount, total and by component |
| auto_make, auto_model, auto_year | Vehicle make, model, and year |
| fraud_reported | Target variable — whether the claim was fraudulent (Y/N) |

## Engineered Features (added during cleaning)

| Column | Description |
| --- | ---: |
| grouped months | Customer tenure bucketed into ranges (0–2, 2–5, 5–10, 10+ years) |
| grouped age | Customer age bucketed into 6 brackets (19–25 through 54+) |
| time grouped | Incident hour bucketed into Morning / Afternoon / Evening / Night |
| incident year | Extracted from `incident_date` |
| vehicle age | Incident year minus `auto_year` |

**Note:** `_c39` was a fully blank column present in the original raw export and was dropped during cleaning.
