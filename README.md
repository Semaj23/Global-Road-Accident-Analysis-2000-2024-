# Police Investigation SQL Case Study
This project is a **SQL-driven investigative case study** that simulates a real-world crime analysis scenario.  
A murder occurred on **January 15, 2014**, and the objective was to uncover the perpetrator by querying and analyzing data from a police department’s **relational database**.

<img width="781" height="566" alt="Police Investigations SQL" src="https://github.com/user-attachments/assets/06ca588c-191b-4b1f-acc5-8b3df27be9d4" />

Using structured SQL queries, I followed digital evidence trails across multiple tables—including crime reports, interviews, and personal records to logically deduce the suspect and ultimately identify the **mastermind behind the crime**.

This project demonstrates how **SQL can be used as a powerful investigative and analytical tool** to solve complex, multi-step problems.

---

##  Dataset Description

The investigation was conducted using a **fictional police database** containing interconnected tables:

- **`crime_scene_report`** – details of reported crimes  
- **`person`** – personal data of individuals  
- **`interview`** – transcripts of witness and suspect interviews  
- **`drivers_license`** – physical descriptions and vehicle details  
- **`facebook_event_checkin`** – social and event attendance records  

Each table contributed critical clues that guided the investigation forward.

---

##  Objectives

- Identify the suspect involved in the **murder on January 15, 2014**
- Validate the suspect using **multiple independent data sources**
- Determine whether the suspect acted **alone or on behalf of someone else**

---

##  Investigation Process (SQL Walkthrough)

### 1️⃣ Crime Identification

The investigation began by confirming the crime details— type, date, and location —from the crime scene reports.

```sql
SELECT *
FROM crime_scene_report
WHERE date = '20140115'
  AND type = 'murder';
This query established the foundational context for the case.


2️⃣ Witness Discovery
Based on the crime scene description, potential witnesses were identified using address-based filtering.

SELECT *
FROM person
WHERE address_street_name = 'Northwestern Dr'
ORDER BY address_number DESC;
This step helped isolate individuals most likely to have firsthand information.


3️⃣ Interview Analysis
Witness interview transcripts were analyzed to extract key clues related to:

Physical appearance of the suspect

Vehicle descriptions

Behavioral patterns

SELECT *
FROM interview
WHERE person_id = <witness_id>;
These insights significantly narrowed the scope of the investigation.


4️⃣ Suspect Narrowing
Using witness descriptions, the suspect pool was filtered through driver’s license data based on:

Hair color

Gender

Height

Vehicle make


SELECT *
FROM drivers_license
WHERE hair_color = 'red'
  AND car_make = 'Tesla';
This step dramatically reduced the number of viable suspects.

5️⃣ Event & Behavior Correlation
Social activity data was then used to validate suspect behavior and confirm patterns described during interviews.

sql
Copy code
SELECT *
FROM facebook_event_checkin
WHERE person_id = <suspect_id>;


## 6️⃣ Final Revelation

Further analysis revealed that the identified suspect was acting on behalf of another individual, leading to the discovery of the true mastermind behind the crime.

This conclusion was reached by systematically combining insights from multiple independent data sources, including:

- Interview confessions that hinted at external influence  
- Financial and social influence indicators suggesting indirect control  
- Behavioral consistency across datasets that aligned actions with motive  

By correlating these signals across relational tables, the investigation moved beyond identifying the executor to exposing the orchestrator of the crime.

---

##  Key Findings

- Successfully identified the direct perpetrator of the murder  
- Uncovered the true individual responsible for planning and influencing the crime  
- Demonstrated how relational joins and logical filtering can solve complex, multi-step investigative problems  

---

##  Skills Demonstrated

- Advanced SQL querying  
- Multi-table joins and relational analysis  
- Logical problem decomposition  
- Pattern recognition across structured datasets  
- Real-world analytical and investigative thinking  

---

##  Tools & Technologies

- SQL (SQLite-style syntax)  
- Relational Databases 
- Analytical Reasoning & Data-Driven Investigation 

---

##  Why This Project Matters

This project closely mirrors real-world data analysis scenarios where:

- Information is incomplete or fragmented  
- Insights must be logically inferred, not explicitly stated  
- Multiple data sources must be combined to form reliable conclusions 

It highlights my ability to think like an analyst go beyond surface-level queries, and transform raw data into meaningful, actionable insights.



