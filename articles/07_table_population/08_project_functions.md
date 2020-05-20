# Project Functions

Fabric Project functions are user-defined Java functions that are added to the Project implementation to perform complex data manipulations or to execute queries on a specific Instance ID . Project functions can be either connected in a map (Table Population or Parser), to other Fabric objects or invoked from another function using Java code.
Functions can be created in Logical Units , References, Web Services, Shared Objects  or from existing Table Populations . A function can be defined as a Shared Object  and can be used in any object  in a Project. If a function is defined within an LU, Reference or Web Services, it is accessible only within that specific object.

### Project Function Types

**Regular Function**
*	A function that executes the business logic required within a Project and can be invoked from any Fabric object like a Table Population , Parser , Web Service  or from another function. 
*	A Regular function has a specific category known as an Enrichment function  which is executed once all LU Tables have been populated to extract data from any LU Table and use it as needed. An Enrichment function must not have Input parameters and must not return any value.

**Root Function**  
*	A function that is used as a source object to trigger the Table Population  mechanism.
*	The output of a Root function serves as input for the Table Population. This function cannot be used for data-mapping logic.
*	A Root function must have at least one Input parameter and at least one Output parameter. The Root function of a root table must have only one parameter.

Click for Code Examples of a Root Function .

**LUDB Function** 
*	A function that is invoked from an SQL query to perform more complex logic operations on LU data than those performed using standard SQL statements.
*	An LUDB function is invoked from an SQL statement.
*	An LUDB function must have at least one Output value.

Click for Code Examples of an LUDB Function . 

**Decision Function**  
*	A Function that assess whether a sync  is performed on an LUI. 
*	A Decision function can be defined on LU Schema , LU Table  or Table Population  levels. 
*	A Decision function must have no Input parameter and return a Boolean (True or False) parameter. An LUI Sync is performed or not performed based on the returned result. 

Click for Code Examples of a Decision Function .

**Switch Function**
*	A specific Fabric Project function used by Parsers  to split records to populate more than one record type in the Parser map.
*	A Switch function enables users to define different types of records for the same parser.

**User Job**  
*	A specific Fabric function used by the Job’s mechanism. Jobs can only invoke functions of this type.