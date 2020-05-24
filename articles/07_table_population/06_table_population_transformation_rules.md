# Table Population Transformation Rules

Data Transformation rules can be applied during the [LU Table Population](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/07_table_population/01_table_population_overview.md) process in a number of ways using the following tools: 
*	[Functions](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/07_table_population/08_project_functions.md).
*	[Translations](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/09_translations/01_translations_overview_and_use_cases.md).
*	[Globals](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/08_globals/01_globals_overview.md).
*	Constants.
*	[Lookup Tables](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/07_table_population/11_lookup_tables.md).

Data Transformation is performed from the source object’s data to the target LU Table’s data. Since the source object includes one or more records, the transformation is applied on each source record. 
When defining Data Transformation rules, the object’s Input and Output fields must be connected to a source table, target table and/or other objects in the population, as displayed in the following example: 

![image](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/07_table_population/images/07_06_01_screen.png)

Data Transformation rules are set in the Table Population or [Parser Map] in the Objects tab in the Table Population or Parser Map windows. 

![image](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/07_table_population/images/07_06_02_objects_menu.png)

### Functions
Functions can be added to a Table Population map to apply various data transformations. There are two types of functions: 
*	[**Built-in functions**](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/07_table_population/07_fabric_built_in_functions.md) that are part of the Fabric infrastructure. They can perform standard transformation of dates, strings, or basic mathematical operations.
*	[**Project  functions**](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/07_table_population/08_project_functions.md) that are created specifically for the current project and can perform more complex logic. 
Both Built-in and Project functions can be either connected in a map (Table Population or Parser), to other Fabric objects or invoked from another function via Java coding.
Note that [root functions](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/07_table_population/03_creating_a_new_table_population.md) which are also displayed in the Objects tab can only be used as a source object and not for Data Transformation. 

### Translations and Globals
 
[Translations](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/09_translations/01_translations_overview_and_use_cases.md) and [Globals](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/08_globals/01_globals_overview.md) can be added to a Table Population map to transform the data from one set of values to another. Translations and Globals are defined either under an [LU](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/03_logical_units/01_LU_overview.md) or under [Shared Objects](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/04_fabric_studio/12_shared_objects.md). Those defined under Shared Objects  are available for all LUs in a project.

### Constants
 
Constants are hard-coded values that can be used in a Table Population map to set a constant value. The scope of a constant is in the current Fabric object where the constant is defined. Constants are not managed as variables in Fabric and cannot be used by various Fabric objects.

To add a constant to the Table Population:
1.	Right click in the **Table Population** working area and select **Insert Constant Value** to add the constant to the map.
2.	Set the **Constant’s Name** and **Value** by editing the **Object** in the **Table Population**.
3.	Connect the **Constant** to the **Object** in the **Table Population** to a column in the target **LU Table** or to another Fabric object.

To modify a constant, double click it and edit the **Value**. 

To delete a constant, select it in the **Table Population** and press **Delete**. 

### Lookup Tables

[Lookup Tables](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/07_table_population/11_lookup_tables.md) can be added to a Table Population map to get additional information about each record retrieved from the source object. A lookup can retrieve data from a Source DB Table, an [LU Table] or from a [Reference] Table. 

For improved performance, it is recommended to create lookups based on an LU Table and not a DB Table. The reason is that an LU Table is usually much smaller than a Source DB Table since it includes only data relevant and/or applicable for an LU. In addition, the LU Table is kept in the Fabric memory and is faster to retrieve. 

A lookup returns only one record for each input record. For example, if the population needs to get a customer’s bills and to add a billing address to each record, define the Address table as a lookup table connected to the Bill table.

[![Previous](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/images/Previous.png)](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/07_table_population/05_table_population_mode.md)[<img align="right" width="60" height="54" src="https://github.com/k2view-academy/K2View-Academy/blob/master/articles/images/Next.png">](https://github.com/k2view-academy/K2View-Academy/blob/master/articles/07_table_population/07_fabric_built_in_functions.md)