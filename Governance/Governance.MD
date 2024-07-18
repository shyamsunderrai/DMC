# Data Governance Notes
#### Data Owner: Entity that owns the data, for instance HR department owns all the HR data
     However, there is shared responsibiliy with other departments
     1. Human resources
     2. Information technology: Design & manage the systems which HR data will be operated/stored under
     3. Information security: Will secure, enforce integrity and confidentiality of the data
     4. Legal team: Will help keep tabs on the legal impacts associated with the data
     5. Data analytics: Protect quality and enable BUs to take decision


```mermaid
flowchart LR
A[Data Owner] -->|Delegates| B(Data Stewards)
B(Data Stewards) --> |Alias| C(Data Controllers)
C(Data Controllers) --> |Represent| D(Data Processors)
C(Data Controllers) --> |Retailer And CreditCardServiceProvider | E(Data Processors)
```

There are three key strcutures from the perspective of Data Governance.

```mermaid
stateDiagram-v2
Data-Owner --> Data=Stewards --> Data-Custodians
```
