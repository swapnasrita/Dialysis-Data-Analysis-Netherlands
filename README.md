# Dialysis-Data-Analysis-Netherlands
**Dataset**

The dataset originates from the kidney atlas, an initiative aimed at mapping information about care and associated costs for individuals with kidney disease in the Netherlands, including regional variations. It is generated using data from the Vektis database, which contains declared healthcare data for nearly all residents of the Netherlands.
The dataset provides detailed insights into:
The number of kidney patients in the Netherlands and across different regions.
Associated healthcare costs, including hospital care and medication use.
Clinical outcomes and coexisting conditions for both kidney patients and the general population (for comparison).
One of the key features of this dataset is its focus on secondary care data, with the ability to trace patients with kidney disease using diagnosis-treatment combinations (DBCs). This enables a granular analysis of the types of care provided and the financial implications.
Data is updated annually, covering the period from 2012 to 2021, and is managed by Nefrovisie, the quality agency for kidney care in the Netherlands. By leveraging this dataset, researchers and policymakers can gain valuable insights into trends, costs, and healthcare delivery for individuals with kidney disease, enabling evidence-based decisions to optimize care and allocate resources effectively.
The kidney atlas is publicly accessible via nieratlas.nl, where the data is visualized and made available for research and policy analysis. Its open nature supports transparency and facilitates data-driven improvements in kidney care.


**Why this dataset?**

Since 2020, during my postdoctoral studies, I have focused on improving dialysis methods, specifically through a sorbent-assisted peritoneal dialysis (PD) model. My aim has been to enhance patient mobility and overall quality of life—key factors for improving long-term outcomes for kidney patients.
Peritoneal dialysis (PD) offers several advantages over hemodialysis (HD), including greater flexibility for patients and potentially fewer hospital visits. However, while quality of life is challenging to quantify directly, cost-effectiveness is measurable. This dataset is particularly valuable because it provides detailed information on healthcare costs for both HD and PD. By analyzing this data, I can validate the notion that PD is not only a gentler alternative but also a more cost-effective one compared to HD.
Additionally, the dataset's granularity—covering care costs, medication use, and outcomes—offers a comprehensive view that supports both regional and national healthcare decision-making. It aligns directly with my research focus and provides a data-driven foundation for advocating for improved dialysis options.

Data Cleaning and Analytics
The following notation is used in this section
Red: Power BI tools
Black: Results




Rename Columns to English (30 minutes)

The column names were translated into English for better clarity and usability (PD_P1_T1).
Data Understanding
The dataset was cleaned and organized by creating two separate tables specifically for PD and HD.
Filters were applied to ensure the tables contained only data relevant to PD and HD modalities.
Null values were removed.
All the grouped values for the columns sex (M+V), dialysis modality (Alle), age group (Alle 20+) were removed.
The control group was removed as it did not matter to the objective.
The dataset was evenly distributed across key demographic variables such as sex, treatment modality, and age group.
Cost Analysis

The primary purpose of this data processing was to prepare the dataset for cost calculation and analysis. The columns pertaining to average costs were kept. 
Custom columns are created for each category by multiplying the number of patients for the cost category.
The columns were then grouped according to the dialysis modality sublevel (Home, in-center, APD, CAPD).
I compared the costs accrued in year 2013 to year 2020, 2020 being the COVID year - I assumed that there will be significant changes.
I noticed in the cost analysis that a major % of costs went to specialist costs and medication costs. 
In 2020, there was a general increase in prices due to inflation but also the percentage of visit to mental health specialists increased substantially. Transportation was a lower fraction than in 2013 due to quarantine in Netherlands and general reluctance of the patients to be in public.
Comparing the dialysis costs, in-center HD is the most expensive dialysis modality and PD costs were lower in general be it APD or CAPD (I have a review on different forms on PD, read here). 
Looking at other countries (table 1), I see the same trend of HD costing more and home HD providing a cheaper alternative.
Table 1: Costs of dialysis across different countries. 
Study link
Country
Size of study
Dialysis Modality
What is included?
Costs
Study Year
Year published
Patient Category
Model
https://link.springer.com/article/10.1186/s12882-019-1421-z
Australia
725
HD, PD
Treatment, consumables, labor, medications, transport, utilities, capital costs, equipment, staff accommodation
HD:$53,126.31
HHD:$26,543.06
PD:$36,165.51
2017
2019
Adult
-
https://doi.org/10.1016/j.xkme.2020.12.003
Canada
39318
79% HD
21% PD
3X in center HD
PD
Labor, equipment, drugs, overhead, hospitalization
HD: $35,271.2
PD: $33,630.9
2004-2013
2021
Adult
Markov model
https://doi.org/10.21037/atm-21-1100
China
1407
HD + Hemoperfusion (HD + HP)
HD
Unit cost, labor, treating complications
HD + HP: $101,034.61
HD:$69610.56
2014-2016
2021
Adult
Markov model
https://doi.org/10.1111/1744-9987.13620
Colombia
81
HDx (expanded HD by medium cut-off dialyzers)

High flux HD (HD HF)
Hospitalizations,
medications
HDx:$2049.42
HD:$2642.32
2019
2021
Adult
-
https://doi.org/10.3390/ijerph192114007
Germany
872 (50% HD, 50% PD)
HD, PD
Healthcare, transport, hospitalisation
HD: $48,729.47
PD: $47,430.73
Transport HD - PD = $7,181.03
2013-2016
2022
Adult


https://doi.org/10.1186/s12913-023-10154-x
Ghana
-
HD
Labor, equipment, hospitalization, procedures, building costs, utilities, transport, loss of productivity
HD 3X: $8408.4
HD 2X: $5605.6
2022
2022
-
-
https://journals.lww.com/sjkd/fulltext/2012/23010/the_cost_of_hemodialysis_in_a_large_hemodialysis.14.aspx
Saudi Arabia
200
HD
Consumables, equipments, labor, medications, procedures, overhead
$46,332
2007-2010
2012
Adult (1 child included)
-
https://doi.org/10.1111/hdi.12994
UK
-
SC+ HD
3X
3.5X
Labor, equipment, consumables, overhead, transport
3X home: $32,458.38
3X in center:$36,840.73
3.5X home:$36,391.11
3.5X in center:$44,090.68
2019
2022
-
Cost minimization model
transport
home:$324.16
In center:$4,598.41
https://doi.org/10.1177/08968608211061126
UK
-
CAPD
APD
Home HD (HHD)
Labor, overhead, equipment
CAPD: $18,179.93
APD:$22,932.70
HHD:$25,177.47
2018-2019
2022
-
-
https://doi.org/10.1681/asn.2022020221
US
16610
(50% HD, 50% PD)
In center HD, PD
Medications, rehabilitation, non-dialysis expenditures
HD: $108,656
PD: $91,176
2008-2015
2022
Adult
-
https://doi.org/10.1016/S0272-6386(01)80127-X
US
197
In center HD, Short Daily in center HD, Nocturnal HD, Short daily home HD
Dialysis, hospitalisation, EPO, medication, other
HD: $68,400
SD HD: $60,800
N HD: $57,700
SDH HD:$57,400
-
2001
Adult
-





Medication Analysis
The primary purpose of this data processing was to prepare the dataset for average patients on medications. The columns pertaining to this were kept. The data related to RAAS, ACE inhibitors, diabetes, insulin, and other medications that were present in nieratlas was further categorised into 5 categories. Conditional formatting was used on the unpivoted medicine column to assign different drugs to these 5 categories (medicine_category).
Patients are always on renal medications (vitamins, phosphate binders, erythropoietin-stimulating agents (EPO) etc), cardiovascular medications (statins, ACE inhibitors, RAAS, etc), diabetes medications (SGLT2 inhibitors, metformin), symptom management medications (antacids, antidepressants, laxatives etc) and other medications (immunosuppressants etc)[10.1093/ajhp/52.17.1895].  Comparing medications between canada [https://journals.sagepub.com/doi/full/10.1177/2054358120912652] and NL. In Canada, on average PD  and HD patients take 16.7 and 18.1  medicines per patient, majority being symptom management medications [https://doi.org/10.1177/2054358120912652]. In US the median medications per patient is 12 [https://doi.org/10.1093/ndt/gfh280]. In Germany, the median number is 8 [https://academic.oup.com/ckj/article/12/5/663/5498601].
Literature from the other sources were collected in separate CSV files and used for comparison.
The most prescribed drugs are cardiovascular and renal medicines. In all countries (includes DOPPS study and PDDOPPS study), we see about half of the patients on some kind of medication. With the high medication burden in dialysis patients often stop using medications and adherence is a really concern. In the new device that I am modelling in collaboration with Nanodialysis and Utrecht University, there is significant decrease in phosphate binder medications (which are often too big and patients generally dislike them).
I also see significant high use of medication in Canada. As far as I know the data is collected in the British Columbia renal registry so maybe the prescription is just unnaturally high in that province.


Specialist Analysis
The primary purpose of this data processing was to prepare the dataset for average patients going to specialists. The columns pertaining to what different specialist patients went to were kept. Table was grouped by sex, age group, dialysis modality and then unpivoted to get the list of specialists in one column. 
Patients often have to go to multiple clinicians to address the various comorbidities that arise with Dialysis. Dialysis also takes a significant toll on mental and physical health. Across all populations, around 60% patients visit cardiologist as the increased pressure on the kidney puts increased pressure on the heart.  In the older population, there is a rise in visits to physiotherapists and dieticians to keep control of the muscles (fluid overload is hard on patients) and diet (less protein and phosphates). 
