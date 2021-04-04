# Project and Billing 
- GCP Projects form the basis for creating, enabling and using all GCP Services including managing APIs, enabling billing, adding and removing collaborators, and managing permissions for GCP resources.
- Project are logical units which consumes a bunch of resources.
- The Project associated with account and accounts with organization.
- Project = Resource + Setting + Metadata
- The Project associated with or defined by 3 piecees of Metadata
  - name, ID and the number.
- Project ID is unique & permement.

## Organization 
- It is root node in GCP hierarchy (super node)
- Organizational ID is unique identifier, automatically created.

    ![Relationship Project & organization](https://user-images.githubusercontent.com/56934817/113521817-51449380-95b5-11eb-9c85-17c49b66c948.png)

<img align="center" src="https://user-images.githubusercontent.com/56934817/113521817-51449380-95b5-11eb-9c85-17c49b66c948.png"> 

## Billing Alert
- Message with certain amount of billed
- Can be on project or plan

### Billing Account
- Who will pay for 
- Access control to biling account is established by cloud IAM roles
- BA can be linked to one or more project 
## Billing Account TYpe
1. Self Serve 
   1. When billed , it will be charged
   2. cost are charged automatically
   3. by Credit or debit card
2. Invoiced 
   1. After month end 
   2. Wire transfer or check 
   3. Invoices are mailed.


## Billing Account Charging Cycle 
- Monthly Billing 
  - cost are charged on regular Monthly cycle
- Threshold Billing 
  - Cost are charged when your account has accured a specific amount 
- Invoiced billing account arre always billed monthly. 
=
### Billing Contracts
- A BA includes a set of contract, defines on Google payments profile
- user can manage those contract through GCP console of the payment console 

##### Billing Sub-account 
- Allows user to group charges from projects together on seprate section of Invoice

= 
### Relationship between Organization, Projects, billing accounts & payment

1. Ownership refers to Cloud IAM permission inheritance.
2. payment linkages define, which account pays for a given projetc.

![image](https://user-images.githubusercontent.com/56934817/113522129-a08bc380-95b7-11eb-9e3a-13a754cb32e7.png)

- in diagram, the organizzation hsa owenership over the billing account & project 1,2,3 means it is cloud IAM permission parent of 3 Projects
- BA is linked to Projects 1,2 &3 
- The billing account is connected to a google payment profile 
- Although you can link billing account to project, billing account are not parents of Cloud IAM , so project dont inherit permissions form biling account they are linked to .














==========================
