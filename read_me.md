# **Stress_Detection_of_Medical_Practitioners**

## **Selection of topic:**

- **Stress Detection of Medical Practitioners**

## **Reason why we selected our topic**

- We can use this type of data to predict the stress levels of medical practitioners to help figure out which reasons affect the most to the practitioners. After having found out the major causes that lead to their high stress levels, recommendations to lower down the stress levels in those areas can be made. In this toughest time, there has been a toil on the health of health care / medical practitioners. This analysis may prove beneficial to the medical organizations to channelize their manpower in an improved manner to ensure good health of those who take of health of rest of the population.

## **Description of our source of data**
- The dataset is the response collected from various medical practitioners to analyse their stress levels in the work space with the help of a questionnaire. The data is been collected from 1Lakh medical practitioners for 30 attributes who are working in private sector and public sector hospitals. 

    Dataset contains the following attributes and the different options given to each question is mentioned in the brackets with the corresponding numerical representation in the dataset.

    ### **Attribute Information:-**
       
    - #### **Features and Target Variable**

    1. Age [30-40 = 1, 40-50 = 2, 50-60 = 3]
    2. Gender [Male = 1, Female = 2]
    3. Sector [Public = 1, Private = 2]
    4. cworkingsamesector [Below 5 years = 1, Above 5 years = 2]
    5. Specialization [Counselor = 1, Anesthetic = 2, Casualty medical officer = 3, Critical Care Medicine = 4, Fetal medicine = 5, General Practitioner = 6, Gynaecology = 7, Neurology = 8, Paediatrics = 9, Pathology = 10, Radiologist = 11, Surgeon = 12]
    6. Work_hours [5hrs = 1, 10hrs = 2, More than 10hrs = 3]
    7. Workyearsspan [Below 5 years = 1, Between 5 to 10 years = 2, Above 10 Years = 3]
    8. Patientperday [Below 10 = 1, Between 10-20 = 2, Between 20-30 = 3, Above 30 = 4]
    9. Overtimeworkinterest [Yes = 1, No = 2]
    10. Overtimeworkpaid [Yes = 1, No = 2]
    11. Stressedduringwork [Sometimes = 1, Very Often = 2, Never = 3]
    12. Feelingonjob [1 = I am completely happy and enjoying the job, 2 = I sometimes feel dissatisfied but generally enjoy my job, 3 = Most of the time I do not enjoy my work, 4 = I have no interest at all in my work]
    13. Sourceofstress [ Over work = 1, Family Issues = 2, Hospital Management = 3, Patitent Attitude = 4, All above in different proportions = 5]
    14. Handling_stress [Talking to an expert = 1, Taking a sleep = 2, Drugs / Alcohol / Smoking = 3, Talking to your family members = 4, Talking to the employer = 5]
    15. InformManagementproblems [Yes = 1, No = 2]
    16. Managementinitiativeto_problems [Taken but was not effective = 1, Effective method was imposed = 2, No action was taken = 3]
    17. Hospitalcaretowards_stress [Counselling = 1, Rearranging the work timing = 2, Refreshments = 3, No care was given = 4]
    18. Stressaffectingpatient_care [ Yes = 1, No = 2]
    19. Stressaffectingconcentration [Very often = 1, Somewhat = 2, Never = 3]
    20. Efforttoreducestresstoimproveconcentration [No effort = 1, Some effort = 2, Lot of effort = 3]
    21. Stressduetotoomany_duties [Yes = 1, No = 2]
    22. Stressdueto_age [Yes = 1, No = 2]
    23. Stressreasonfamily [Yes = 1, No = 2]
    24. Stressdueto_competition [Yes = 1, No = 2]
    25. Prefertostay_alone [Yes = 1, No = 2]
    26. Prefertakingresponsibilities [Yes = 1, No = 2]
    27. Alcohol_usage [Daily = 1, Occasionally = 2, Sometimes = 3, Never = 4]   **TARGET VARIABLE**
    28. Stressnervoushabits [Daily = 1, Occasionally = 2, Sometimes = 3, Never = 4]
    29. Stressmakesnervous [Yes = 1, No = 2]
    30. Stressaffectsemotions [Very often = 1, Somewhat = 2, Never = 3]

Dataset source : 
https://www.kaggle.com/alwinjoseph/stress-detection-of-medical-partitioners

## **Question we hope to answer with the data**
-  We want to predict the impact of the stress levels of Medical Practitioners upon their resorting to **ALCOHOL_CONSUMPTION** based upon their stress causing conditions and the effects of stress on other day to day professional and personal performance, lifestyle and mental health.