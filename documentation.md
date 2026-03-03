# Technical Documentation: Frostbite & Hypothermia Analysis 

## 1. Key Insights

###  Demographic Characteristics & Gender Risks
* **Male Dominance:** Men account for **85% of all hospitalizations**, indicating significantly higher exposure to extreme low temperatures, likely due to occupational hazards or lifestyle factors.
* **The Mortality Paradox:** Despite lower hospitalization volume, the **mortality rate for women is 22%**, compared to 13.5% for men.
* **Biological Vulnerability & Anatomy:** Women are statistically more prone to rapid **Hypothermia (T68)** due to physiological differences:
    * **Surface Area to Mass Ratio:** Women generally have a higher surface-area-to-mass ratio, leading to faster heat loss to the environment.
    * **Muscle Mass vs. Thermogenesis:** Lower average muscle mass compared to men results in less "shivering thermogenesis" (the body's primary way of generating internal heat).
    * **Subcutaneous Fat Distribution:** While fat acts as an insulator, different distribution patterns can affect how core temperature is maintained during prolonged exposure.
* **Diagnosis Type by Gender:** These anatomical factors explain why women are predominantly diagnosed with systemic cooling (**Hypothermia**), which carries a higher immediate fatality risk, whereas men more frequently present with localized **Frostbite (T34)**.

  

###  Clinical Trend Dynamics (2021–2025 Focus)
* **Shift in Medical Events:** Since 2021, there is a visible downward trend in localized frostbite (T34), while systemic hypothermia (T68) has been rising since 2022.
* **Root Cause Analysis:** This shift suggests changing demographics in high-risk groups (e.g., an aging population more susceptible to systemic cooling than localized extremity injuries).

###  Age Group Protection
* **Pediatric Outcomes:** Mortality among children is significantly lower (**2.6%**) than in adults (**15%**). This is likely due to faster guardian intervention, prioritized emergency protocols, and different physiological responses.

###  The Pandemic "Rebound Effect"
* The sharp decline in 2020 followed by a surge in 2021 suggests a **"diagnostic gap"** during the COVID-19 lockdowns, where many cases from the first year entered the system with a delay.

---

## 2. Data Transformation & Power Query Process

###  Data Acquisition & Cleaning
* **Source Management:** Raw clinical datasets were imported and stripped of redundant aggregate records to ensure granular accuracy.
* **Handling Suppressed Data ("<5"):** To maintain mathematical continuity, values originally marked as "<5" (for privacy) were replaced with a constant numerical value of **2**. This enabled statistical operations while keeping the margin of error acceptable.
* **Label Normalization:** Long medical descriptions were shortened (e.g., "Frostbite involving multiple body regions..." became **"Multiple/Other Frostbite"**) using *Replace Values* to enhance dashboard readability.

---

## 3. Data Modeling & DAX Analytics

###  Advanced Measures
I developed a suite of DAX measures to handle complex calculations. Example of a safe division measure:

```dax
Mortality Rate  = 
DIVIDE(
    [Total Deaths], 
    [Total Hospitalized], 
    0
)
