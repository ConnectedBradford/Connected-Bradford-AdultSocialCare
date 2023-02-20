# Hello
<a href="https://www.bradfordresearch.nhs.uk/our-research-teams/connected-bradford/">
  <img align="left" alt="ConnectedBradford" width="55px" src="https://github.com/ShoreRob1/Images/blob/main/CB%20logo%201.png?raw=true" />
</a>


![](https://visitor-badge.glitch.me/badge?page_id=ConnectedBradford.FDM_AdultSocialCare)

This is the **Connected Bradford Adult Social Care** GitHub page where you can find a summary of the dataset(s), data dictionaries and helpful code.


This dataset and page is maintained by [Robert Shore](https://actearly.org.uk/team_member/rob-shore/): 


:e-mail: [email](mailto:robert.shore@bthft.nhs.uk)

:speech_balloon: ask me about anything, I'm happy to help;


# Adult Social Care

📌 *The adult social care FDM is made up of three source tables (summarised below and data dictionaries linked) from routinely collected adult social care data by City of Bradford Metropolitan District Council (CBMDC) for 48,375 individuals and their contacts, assessments and service types and dates.* *The Assessment and Contacts table range from 2017-2020, while the Services table covers 2008-2020*.

*The source tables are largely populated by fields with the prefix 'src_'. When you see the 'src_' prefix, this means that field has not been reformatted by the Connected Bradford team and it is included in its raw form.*

📁 **What is an FDM?**

*Connected Bradford has adopted the OMOP Common Data Model (CDM) for the majority of its patient-centred healthcare data. Some datasets in Connected Bradford have features that do not sit well within either the OMOP conceptual vocabulary or the structure of the CDM. The aim of the Flexible Data Model (FDM) is to provide a set of design principles and a data model for non-OMOP datasets such that they can be structured and annotated in an OMOP-friendly way, and are therefore easy to combine with OMOP CDM data during analysis.*

*The Connected Bradford Flexible Data Model enables researchers to link standardised datasets and tables across different areas, e.g. primary care, social care and education. In order to be linked to a CDM or clinical dataset, FDMs are designed in the same way as a full CDM, to standardize the structure and content of observational data and to enable efficient analyses that can produce reliable evidence. This also helps any researcher familiar with CDM and OMOP vocabulary to replicate analysis on the Connected Bradford platform.*

[OMOP guidelines here](https://ohdsi.github.io/CommonDataModel/cdm60.html)


### Standard FDM tables included in this dataset


🧍 **person**

48,375 individuals 

*This table serves as the central identity management for all Persons in the database. It contains records that uniquely identify each person or patient, and some demographic information. All records in this table are independent Persons. All Persons in this database have one record in this table, unless they fail data quality requirements specified, e.g. an event from the source tables pre-dates their date of birth or exceeds any date of death by more than 42 days (42 days is the time period allowed due to processing of deaths).*

*The BIRTH_DATETIME field is standardised across all Connected Bradford FDMs and is equivalent to the content of BIRTH_DAY, BIRTH_MONTH and BIRTH_YEAR (DD-MM-YYYYT00:00:00). The person’s death date is also stored in this table in the same standardises format. The validated minimum and maximum of additional ‘event’ dates are stored in the observation_period table, while all validated 'events' are stored in the visit_occurence table.*

*The person table also includes demographics such as ethnicity and gender.*

*Use fields from the person table for all analysis related to birth, death and any demographics*




🔎 **observation_period**

48,375 individuals 


*The observation_period table contains records which define spans of time during which two conditions are expected to hold: (i) Clinical Events that happened to the Person are recorded in event fields in the source tables and visit_occurence and (ii) absence of records indicate such Events did not occur during this span of time.*

*The validated minimum and maximum of additional ‘event’ dates are stored in the observation_period table, while all validated 'events' are stored in the visit_occurence table. observation_period records can be as short as a single day.*


🏥 **visit_occurence**

220,938 records


*The visit_occurence table contains Events where Persons engage with adult social care for a duration of time. They are often also referred to by OMOP as 'Encounters'. Visits are defined by a configuration of circumstances under which they occur, such as whether the patient comes into contact  with social care, the other way around, or the interaction is remote. All validated 'events' are stored in the visit_occurence table.*

### Source tables in this dataset

*There are three source tables in this dataset. Source tables are those that have had little to no manipulation other than to validate any event dates. All source field are prefixed with 'src_'. The three source tables in the adult social care data set are:*

### src_Assessments

*The Assessment table collects all 'event' records related to a dated assessment by adult social care. There are 4,1084 records (2017-2020) in this table across 26 different types of assessment, ranging from Adult Assessments, Mental Capacity Assessments and Support Plan Reviews.*

### src_Contacts

*The Contacts tables contains 11,3602 records (2017-2019) of any contact and date between individuals and adult social care. Routinely collected data included in this table:*

- *69 different types of contact source (e.g. self-referral, family/friends, police)*
- *14 different types of contact route (e.g. Community, hospital discharge)*
- *37 different contact reasons (e.g. Access Point Screening, Blue Badge applications, Safeguarding)*
- *80 different types of contact outcomes (e.g. Advice, progress to assessment, referrals)*

### src_Services

*The Services table has 40,965 (2008-2020) records for 16 different types of service for each individual (e.g. home care, residential, nursing, respite) and Primary Support Reasons (e.g. physical support, social support, learning disability support) and includes service start and service end dates.*


## Useful links

📖 [Data dictionary](https://github.com/ConnectedBradford/FDM_AdultSocialCare/commit/5e8df93ddfebc503063181d25f4d5495ba5ff36d)  

🏠 [How to define different types of care](code/care_type_definitions)










