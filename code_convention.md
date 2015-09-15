# Code Convention for CI-Agriculture

Code Convention is created to maintain consistency throughout the system. It also increases code readability in case our current programmers goes sleeping with the fishes or to breathe one's last.

We implement general convention from Oracle for Java Language which can be downloaded here : www.oracle.com/technetwork/java/codeconventions-150003.pdf. Please read it thoroughly and make it your standard code guidance in advance of reading the rest of these passage.

In addition to the convention above, we also implement our own rule. For the time being, constructing a naming standard for our code is the only thing that we've done so far. 

## Naming

Our naming standard comprises of element as follows.  
  - Every variables or information should be in **English Language**, except for particular terms that the team decided to be in Indonesian Language.  
  - All variables in code must use camelCase. Example : ```seasonCode```
  - JSON Node or database-representative information uses underscore ```_``` as replacement of whitespace. Example : ```farmer_field``` is the right format to be returned with Json Node.
  - Table name in mysql must use underscore ```_``` as replacement of whitespace and to distinguish the module with its sub-section. Example : ```procurement_distribution_farmer_distribution``` means that this tables consists of **farmer distribution** data in **procurment and distribution** module. Though this format is a little hard to interpret, MySQL uses this format as their naming standard. 
  - Each field that represents the same value must have the same name if it exists in different tables. Example : ```Farmer``` and ```FarmerField``` collection both have ```farmer_name``` as String field and its name should be the same. Cases like ```farmer_name``` field exist in ```Farmer``` table and ```name``` field exist in ```FarmerField``` table while in fact they represent the same value is intolerable.
  - Table name must be in singular forms. Plural form such as ```Farmers``` are not allowed.
  - For our standard web service operation, use ```find```, ```insert```, ```update```, and ```delete``` as our standard naming.

## Code Standard

Our backend services which shapes our REST API comprises of two components, Model and Controller. Several rules of Backend Code that must be implemented as a standard is as follows.
- Every controller-related method that directly serves and called by the routes endpoint should be placed on top of the Class, followed by supporting method which serves as helper and whatnot.
- For POST related command, such as ```insert```, ```update```, or ```delete```, must have an intuitive feedback in case of input mismatch or incorrect type in the user JSON input. The feedback also must be in JSON Format. Take a look at UnitPlanningController for details

There's still some work left to be done on Endpoint URI naming convention and on Code Standard. We will update the docs as soon as we get the chance.