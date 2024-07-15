# Normalization

- Process of organlizing data inside the database
- Eliminate data redundancy and enhance data integrity
- Was first proposed by *Edgar F Codd* as part of relational model 

For instance, if a monolith table is broken down into multiple entities based on their relationship with each other based on key/attribute. Eg. Dept_ID in Departments table = Dept_ID in Employees table. 

#### Key Benefits
- Reduces storage space as redundant data is eliminated
- Ensures data integrity for instance, without a valid Dept_ID inside Department table, Employee.Dept_ID cannot have a new entry.
  [ This is ensured by integrity check ]
- Flexible so can accommodate more changes to the data


## Types of Normalization
1. 1NF
.. A single column should hold single value for each row (atomic)
   | Emp No    | FirstName | LastName   | HireDate   | Project              |
   | :---      |    :----: | :----:     | :----:     |  ---:                |
   | 1         | Thomas    | Jefferson  | 07/04/2024 | Project-1            |
   | 2         | John      | Kennedy    | 07/05/2022 | Project-1, Project-2 | <img src="../Normalization/Normalization-1nf-xmark.png">
   | 3         | Abe       | Lincon     | 07/04/2000 | Project-3            |

.. Should always contain similar data
.. Name of a column should always be distinct
2. 2NF
3. 3NF
4. 4NF
5. 5NF


