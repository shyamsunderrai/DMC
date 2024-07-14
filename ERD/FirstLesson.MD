# ERD

Key terminologies to remember
1. ERD: Entity Relationship Diagram
..Kind of Data store in Database/Current System [ Flat files, Video Files, Row/Columns ] 
..Consumed information from source, type of
..Produced information for Target/downstream, type of
..Organization of relationships and data elements between 1st to 5th Normal Forms
..Define relationships between the elements of current elements within the system
..Cardinality, relationship of one->one OR one->Many or Many->Many
2. ODS: Operational Data Store. A place where data from heterogenous sources are stored. Data is retained for a longer period. 
3. Staging: An additional/optional area between ODS and Current system where data is validated and put into Current System. After data is writtent to current system, its truncated/removed.
4. Data Marts: Subsets of processed data from *Current System* created for the *Downstream applications*

Baseline for any system is the following representation of flow

Source{Upstream Process or System} -> Current System -> Target {DownStream Process or System}

#### Staging area or ODS
Operation Data Store, known very well in short as ODS, is the stage where data is stored between *Source* and *Current System*. 
*Stage" and "Staging" are two different terms. 

Source{Upstream Process or System} -> *[ODS]* ->  Current System -> Target {DownStream Process or System}

#### With change post validation into Staging area

Source{Upstream Process or System} -> *[ODS]* -> *[Staging]* -> Current System -> Target {DownStream Process or System}

#### With Data Marts between Current System and Target/DownStream 

Source{Upstream Process or System} -> *[ODS]* -> *[Staging]* -> Current System -> *[Data Marts {DM1, DM2} ]* ->  Target {DownStream Process or System}



## ERD: What are Objects/Entities
*Entity*: Representation of something we can see/feel or something that can be represented in a structured/semi-structured form, like within a table. Person/People, Cars/Aeroplanes, Events can be entities. 

*Attributes*: Also known as column(s) are one aspect of information that defines the Entity. Like "Number of Doors" for an Entity named Cars or Brand Name, or Price. 

### Types of Entities


