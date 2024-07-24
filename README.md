

# Attrition analysis -Dashboard


## Problem Statement

This dashboard helps organizations understand their employees better.  It helps the HR department know their employees are satisfied with theit work environment and company policies.  Through the different metrics and ratings, they can identify areas needing improvement, and thus they can enhance their HR practices by addressing these areas.  It also provide insights into employee turnover rates, average tenure, and performance metrics.  By identifying these patterns and issues, the organization can work on factors responsible for employee dissatisfaction and retention ultimately improving overall employee engagement and productivity.


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present.
- Step 5 : Calculate the attrition count, employee count to know the active employees, attrition rate, total attrition
- Step 6 : In the report view, under the view tab, theme was selected.
- Step 7 : Since the data contains various ratings, thus in order to represent ratings, a new visual was added using the three ellipses in the visualizations pane in report view. 
- Step 8 : Four card visuals were added to the canvas, for representing number of employees, employees quit, attrition % , active employees and average age. 
           Using visual level filter from the filters pane, basic filtering was used & null values were unselected for consideration into average calculation.
           
           Although, by default, while calculating average, blank values are ignored.
- Step 9 : A bar chart was also added to the report that people quit the company for education qualification. While creating this visual, field named "Gender" was also added to the Legends bucket, thus number of customers are also seggregated according the gender. 
  
In our dataset, Some parameters were assigned value 0, representing those parameters are not applicable for some customers.

All these values have been ignored while calculating average rating for each of the parameters mentioned above.


- Step 10 : Calculated column was created in which, employees were grouped into various age groups.

for creating new column following DAX expression was written;
       
        Active employee = 
        
        if SUM('HR data'[Employee count])-[total attrition],

        Attrition rate = 
        
        if SUM('HR data'[Attrition count])/SUM('HR data'[Employee count]),

        Total attrition = 
        
        if SUM('HR data'[Attrition count]),
        


        
- Step 11 : New measure was created to find total number of active employees.

Following DAX expression was written for the same,
        
        Active employee = if sum('HR data'[Employee count])-[total attrition]
        
A card visual was used to represent Active employee.

![Attrition analysis](https://github.com/user-attachments/assets/49376b1b-a8e0-4878-818f-692734913181)

        
 - Step 12 : New measure was created to find  % of atttrition rate,
 
 Following DAX expression was written to find % of customers,
 
         % Attrition rate = if sum('HR DATA'[Attrition count])/sum('HR data'[Employee count])
 
 A card visual was used to represent Attrition rate
 
![Attrition analysis](https://github.com/user-attachments/assets/d293214c-82fe-405e-92c5-da315fbaf2ac)

 
 - Step 13 : New measure was created to calculate total attrition.
 
 Following DAX expression was written to find total distance,
 
         Total attrition = if sum('HR data'[Attrition count])
    
 A card visual was used to represent employees quit total attrition.
 
 
![Screenshot](https://github.com/user-attachments/assets/cdfcfdb8-0360-4997-a0d3-d7c03891cc70)
 

 
 






 
 # Report Snapshot (Power BI DESKTOP)

 
![Screenshot 2024-07-24 112355](https://github.com/user-attachments/assets/f0ecf484-800b-4e00-8669-63e4068d73ea)


           



