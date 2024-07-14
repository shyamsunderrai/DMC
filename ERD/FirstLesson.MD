#ERD

Key terminologies to remember
- ERD: Entity Relationship Diagram
- ODS: Operational Data Store

Baseline for any system is the following representation of flow

Source{Upstream Process or System} -> Current System -> Target {DownStream Process or System}

#### Staging area or ODS
Operation Data Store, known very well in short as ODS, is the stage where data is stored between *Source* and *Current System*

Source{Upstream Process or System} -> [ODS] ->  Current System -> Target {DownStream Process or System}
