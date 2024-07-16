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
   | Emp No    | Name | Name   | HireDate   | Project              |
   | :---      |    :----: | :----:     | :----:     |  ---:                |
   | 1         | Thomas    | Jefferson  | 07/04/2024 | Project-1            |
   | 2         | John      | Kennedy    | 07/05/2022 | ~~Project-1, Project-2~~ |
   | 3         | Abe       | Lincon     | 07/04/2000 | Project-3            |

   Based on the above observation, Project-1 and Project-2 for *Emp No* 2 is non-atomic. Lets fix that

   | Emp No    | Name | Name   | HireDate   | Project              |
   | :---      |    :----: | :----:     | :----:     |  ---:                |
   | 1         | Thomas    | Jefferson  | 07/04/2024 | Project-1            |
   | 2         | John      | Kennedy    | 07/05/2022 | Project-1            |
   | 2         | John      | Kennedy    | 07/05/2022 | Project-2            |
   | 3         | Abe       | Lincon     | ~~Project-3~~  | ~~07/04/2000~~   |

   All other columns are duplicate for *Emp No* 2, however, now he has unique information for two separate Projects he was associated with.
   *Now* there is another problem with this representation i.e. HireDate has *Project-3* and Project column has "07/04/2000" as values. This conflicts with the principle of columns having       similar data. Lets fix that.

   | Emp No    | ~~Name~~ | ~~Name~~   | HireDate   | Project               |
   | :---      |    :----: | :----:     | :----:     |  ---:                |
   | 1         | Thomas    | Jefferson  | 07/04/2024 | Project-1            |
   | 2         | John      | Kennedy    | 07/05/2022 | Project-1            |
   | 2         | John      | Kennedy    | 07/05/2022 | Project-2            |
   | 3         | Abe       | Lincon     | 07/04/2000 | Project-3            |
   
   Above looks alright, however, fails the third characteristic of an attribute, each column must be unique. Lets fix this.

   | Emp No    | First Name| Last Name  | HireDate   | Project               |
   | :---      |    :----: | :----:     | :----:     |  ---:                |
   | 1         | Thomas    | Jefferson  | 07/04/2024 | Project-1            |
   | 2         | John      | Kennedy    | 07/05/2022 | Project-1            |
   | 2         | John      | Kennedy    | 07/05/2022 | Project-2            |
   | 3         | Abe       | Lincon     | 07/04/2000 | Project-3            |
   
.. Should always contain similar data
.. Name of a column should always be distinct
2. 2NF
.. There are two main traits for 2NF these are 
... It should have all the traits of 1NF
... Column(s) should not have partial dependency

Lets look at an example 
   | Emp No    | Project   | Allocation | ProjectName|
   | :---      |  :----:   | :----:     | ----:      | 
   | 1         | P1        | 100        | Insurance  |
   | 2         | P2        |  25        | Mortgage   |
   | 2         | P3        |  75        | Banking    |
   | 3         | P1        | 100        | Insurance  |


3. 3NF
4. 4NF
5. 5NF


