# Design Stages

There are three main stages in designing the data model

    - - - - - - - - - - - - - - - - - - - - - - - - - - - - 
    \        P H Y S I C A L      D E S I G N             /
     \                                                   /
      \                                                 / 
       - - - - - - - - - - - - - - - - - - - - - - - - -
        \        L O G I C A L     D E S I G N        /
         \                                           /
          \                                         /
           - - - - - - - - - - - - - - - - - - - - -
            \                                     /
             \                                   /
              \      C O N C E P T U A L        /
               \                               /
                \        D E S I G N          /
                 \                           /
                  - - - - - - - - - - - - - -



Step 1 is *conceptual design* which is at a very high level briefing of the logical model
          - This is mostly abstract 
          - Based on use cases and rules around them
          - Can cater to non-tech stakeholder(s)
Step 2 is *logical design* which is the logical representation and is detailed 
Step 3 is *physical design* based on which DDLs are created 



## Conceptual model 

Contains 

1. Real-world entities
2. Relationship between entities (strong, weak, cardinalities)
3. Organlizational scope
4. Business concepts/rules

### Assignment 

Design a conceptual model with below requirements
- Employee Joins a company
- Employee is assigned to a new department
- Employee is assigned one or multiple roles
- Employee is assigned one or multiple projects


### Solution
Entities
- Employee & Company are entities and "Joins" is the relationship
- Department is another entity and "assign" is relationship. Employee to Department is *one-to-many* 
- Roles and "assigned" is relationship with employee. 
- Projects "one-to-many" and "assigned" is the relationship, project is another entity


```mermaid
erDiagram
    DEPARTMENT ||--o{ EMPLOYEE : employs
    EMPLOYEE ||--|| ROLE_ASSIGNMENT : assigned_to
    ROLE ||--o{ ROLE_ASSIGNMENT : contains
    EMPLOYEE ||--o{ PROJECT_ASSIGNMENT : works_on
    PROJECT ||---{ PROJECT_ASSIGNMENT : involves

    DEPARTMENT {
      int id
      string name
    }

    EMPLOYEE {
      int id
      string name
      int department_id
    }

    ROLE_ASSIGNMENT {
      int id
      int employee_id
      int role_id
    }

    ROLE {
      int id
      string name
    }

    PROJECT_ASSIGNMENT {
      int id
      int employee_id
      int project_id
    }

    PROJECT {
      int id
      string name
    }






 
