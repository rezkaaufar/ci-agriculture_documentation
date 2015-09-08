# Code Convention for CI-Agriculture

Code Convention is created to maintain consistency throughout the system. It also increases code readability in case our current programmers goes sleeping with the fishes or to breathe one's last.

We implement general convention from Oracle for Java Language which can be downloaded here : www.oracle.com/technetwork/java/codeconventions-150003.pdf. Please read it thoroughly and make it your standard code guidance in advance of reading the rest of these passage.

In addition to the convention above, we also implement our own rule. For the time being, constructing a naming standard for our code is the only thing that we've done so far. 

## Naming

Our naming standard comprises of element as follows.  
  - Every variables or information should be in **English Language**, except for particular terms that the team decided to be in Indonesian Language.  
  - All variables in code must use camelCase. Example : ```seasonCode```
  - JSON Node or database-pointing information uses underscore ```_``` as replacement of whitespace. Example : ```farmer_field``` is the right format to be returned with Json Node.
  - Collection name in MongoDB must use underscore ```_``` as replacement of whitespace and dot ('.') to distinguish the module with its sub-section. Example : ```procurement_distribution.farmer_distribution``` means that this collections consists of **farmer distribution** data in **procurment and distribution** module.
  - Each field that represents the same value must have the same name if it exists in different collections. Example : ```Farmer``` and ```FarmerField``` collection both have ```farmer_name``` as String field and its name should be the same. Cases like ```farmer_name``` field exist in ```Farmer``` collection and ```name``` field exist in ```FarmerField``` while in fact they represent the same value is intolerable.
  - Collection/table name must be in singular forms. Plural form such as ```Farmers``` are not allowed.

There's still some work left to be done on Endpoint URI naming convention. We will update the docs as soon as we get the chance. See ya later moronic asshole.