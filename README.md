                                                              Introducing Cross-Sheet Filtering in AWS QuickSight
   
The enhanced approach to cross-sheet filtering involves implementing a custom navigation action, leveraging parameters, and applying custom filters to refine data before displaying it on the target sheet.

Below is the step-by-step process to achieve this:

Step 1: Implementing a Custom Navigation Action in Sheet 1
1.	Select the visual in Sheet 1 that you want to use for navigation.
2.	Add a Custom Action with the following settings:
o	Action Type: Navigation Action
o	Target Sheet: Select the destination sheet.
o	Parameters: Leave blank for now (to be configured later).
This step establishes a link between sheets while setting up the foundation for dynamic filtering.

![image](https://github.com/user-attachments/assets/06d4efcc-224a-4971-913a-3e6dbe5e4390)



Step 2: Creating a Parameter for Filtering
Since filtering will be based on a column value, a parameter must be created:
1.	Navigate to the Parameters section in QuickSight.
2.	Create a new parameter based on the column name to store user selections.
3.	Ensure the parameter type matches the data type of the filtering column.
This parameter will act as a bridge between sheets, dynamically holding the selected value.

Step 3: Updating the Custom Action to Store Selected Values
Now, we need to modify the action to store selected values into the parameter:
1.	Update the custom action created in Step 1.
2.	Link the action to the parameter named.
3.	Ensure that when a user selects a value in Sheet 1, it gets stored in the parameter.
This ensures that when users navigate to Sheet 2, the correct filter is applied automatically.

Step 4: Applying Filtering on Sheet 2
To reflect the user’s selection from Sheet 1, a custom filter must be applied in Sheet 2:
1.	Select the relevant visual in Sheet 2.
2.	Add a filter for the column.
3.	Configure the filter with the following settings:
o	Applied To: Single Sheet (All visuals in this sheet)
o	Filter Type: Custom Filter
o	Filter Condition: Equals
o	Use Parameter: Yes
o	Select Parameter: parameter
This ensures that only data corresponding to the user’s selection in Sheet 1 is displayed in Sheet 2.

![image](https://github.com/user-attachments/assets/cf82b02c-bac8-43a1-a2e3-20a3cee50cb3)

![image](https://github.com/user-attachments/assets/c25c32b5-5033-4e93-ae5e-86f778429b34)


Step 5: Testing the Cross-Sheet Filtering
To verify the effectiveness of this implementation:
1.	Navigate to Sheet 1 and select a specific value (e.g., Month 5).
2.	The navigation action should transition to Sheet 2.
3.	Ensure that only data corresponding to Month 5 is displayed in Sheet 2.
By successfully implementing these steps, the QuickSight dashboard now dynamically filters data between sheets, improving navigation efficiency and response accuracy.  
