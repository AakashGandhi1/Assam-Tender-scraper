### Uses of the data
E-procurement system such as the GEPNIC ([Government eProcurement System of NIC-GePNIC](https://gepnic.gov.in/)) digitizes all or part of the procurement process, for example, buyers publishing tenders, potential suppliers submitting bids and buyers evaluating bids and awarding contracts. All of these activities result in the creation of data, typically stored in the database of the e-procurement system.
OCDS describes how to disclose that information as open data in a standardised structure and format. 
Disclosing contracting data using OCDS, encourages the development of reusable tools and methodologies based on OCDS data.


Through Open Contracting Partnership (OCP) designing the Open Contracting Data Standard and working with stakeholders around the globe on procurement reforms, we have identified five key use cases related to procurement data:
- Market opportunities
- Value for money
- Public Integrity
- Service delivery
- Internal efficiency

CDL worked with the Finance Department, Government of Assam to open more than 45,000 tenders awarded by the state (Financial Years 2016-17 to 2022-23) and partnered with OCP to publish the data according to the Open Contracting Data Standard (OCDS).

With our collaboration with the Government of Assam and the Assam State Disaster Management Authority, CivicDataLab has been working towards building solutions to better protect vulnerable communities from extreme weather events through implementing open contracting strategies for better flood-related procurement. 

This model was made possible through CDL collaboration with the Assam State Disaster Management Authority (ASDMA) to combine procurement data with dozens of other datasets, as well as working with Assam’s Finance Department to structure and standardize data on all flood-related procurement from the last five years. 

Read more here - [Improving climate resilience in flood-prone Assam, India - Open Contracting Partnership (open-contracting.org)](https://www.open-contracting.org/2023/09/28/improving-climate-resilience-in-flood-prone-assam-india/)

### Data Composition:
* Fiscal year range: 2016-2017 to 2022-2023
* Geography: Assam, India
* Total number of departments that opened tender: 397
* Data dictionary: The folder [OCDS-mapped-data-v3](https://github.com/CivicDataLab/assam-tenders-data/tree/update_ocds_mapping/data/ProcessedData/ocds-mapped-data/ocds-mapped-data-v3) contains the `.xlsx`, `.json` files with following fields
  <br>
Main

| Title | Path | Data Type | Description |
|-------|------|-----------|-------------|
| ocid  | String | | |
| id | String | | |
| date | Datetime | | |
| tag | String | | |
| initiationType | String | Fiscal Year | The fiscal year in which the tender is applicable |
| buyer/name | String | Organisation Chain | The name of the organization issuing the tender |
| tender/id | String | Tender ID | An id to identify this tender. This can be used to derive the name of the department the tender belongs to. OCID has tender id as its suffix |
| tender/title | String | Tender Title | Title of tender |
| tender/description | String | Work Description | A detailed description of the work or services required in this tender. |
| tender/datePublished | Datetime | Published Date / Publish Date | The date on which the tender was made public. |
| tender/procuringEntity/name | String | Name | The name of the organization issuing the tender |
| tender/items/classification/description | String | Product Category | The primary classification of the product or service required. |
| tender/items/classification/id | String | Tender Product Category ID | A unique identifier for the product category. |
| tender/items/additionalClassifications/description | String | Subcategory | A secondary classification providing more details about the product or service. |
| tender/items/deliveryAddresses/postalCode | String | Pincode | The location and postal code where the tender's products or services are to be delivered / address of procuring entity |
| tender/items/deliveryAddresses/streetAddress | String | Location | |
| tender/value/amount | Float | Tender Value in ₹ | The maximum estimated amount for the contract |
| tender/value/currency | String | Tender Currency | Currency of Tender Value |
| tender/procurementMethod | String | Tender Type | This describes the bidding method. This is a closed code list, therefore Open was converted to limited and global to open. This can be used to gain brief whether the tender is open for international participation. |
| tender/contractType | String | Tender Contract Type | Describes the type of contract this includes: itemRate, Fixed-Rate, ItemWise, EOI, lumpSum, Percentage, Turn-key, Calculated |
| tender/procuringEntity/id | String | | A unique identifier for the procuring entity |
<br>
Tender Identifiers and Submission Terms

| Title | Path | Data Type | Desc |
|-------|------|-----------|------|
| Tender Ref No | tender/identifiers/id | String | Adds information on top of tender id describing the purpose of tender and place |
| External Reference ID | tender/identifiers/scheme: "external" | String | External Reference ID |
| Is Multi Currency Allowed For BOQ | tender/submissionTerms/allowMultiCurrencyBOQ | Boolean | A boolean value indicating whether bids can be submitted with costs in multiple currencies for the Bill of Quantities |
| Is Multi Currency Allowed For Fee | tender/submissionTerms/allowMultiCurrencyFee | Boolean | Similar to the BOQ, this boolean value specifies whether fees associated with the tender can be paid in multiple currencies |
| Form of Contract | tender/mainProcurementCategory | String | Specifies the main category of procurement, which defines the form of contract. |
| Allow Preferential Bidder | tender/submissionTerms/allowPreferentialBidder | Boolean | A boolean value indicating whether the tender allows for preferential bidders. |
| Bid Validity(Days) | tender/submissionTerms/bidValidityPeriod/durationInDays | Integer | The number of days for which a submitted bid remains valid |
<br>
Tender Details and Milestones

| Title | Path | Data Type | Desc |
|-------|------|-----------|------|
| Tender Fee in ₹ | tender/participationFees/value/amount | Float | The fee required to participate in the tender |
| Tender Fee Currency | tender/participationFees/value/currency | String | The currency fee is payable in |
| Fee Payable To | tender/participationFees/description | String | The entity to which the tender fee is payable |
| Fee ID | tender/participationFees/id | String | Unique identifier for the Fees |
| Number of Tenderers | tender/numberOfTenderers | Integer | The total number of entities that have bid for the tender |
| Publish Date | tender/tenderPeriod/startDate | Datetime | The initial date when the tender is published |
| Document Download / Sale Start Date | tender/communication/documentAvailabilityPeriod/startDate | Datetime | The start date for downloading/sale of tender documents |
| Document Download / Sale End Date | tender/communication/documentAvailabilityPeriod/endDate | Datetime | The end date for downloading/sale of tender documents |
| Clarification Start Date | tender/enquiryPeriod/startDate | Datetime | The start date for submitting queries or seeking clarifications |
| Clarification End Date | tender/enquiryPeriod/endDate | Datetime | The last date for submitting queries or seeking clarifications |
| Bid Opening Date | tender/bidOpening/date | Datetime | The date on which bids will be opened |
| Bid Submission End Date | tender/tenderPeriod/endDate | Datetime | The deadline for bid submission |
| Tender Period in Days | tender/tenderPeriod/durationInDays | Integer | Duration of the tender process in days |
| Enquiry Period in Days | tender/enquiryPeriod/durationInDays | Integer | Duration of the enquiry period in days |
| Period Of Work(Days) | tender/contractPeriod/durationInDays | Integer | Duration of the contract period in days |
| Published Date Milestone | tender/milestones/title | String | Various milestones like published date, document download/sale start and end date, clarification start and end date, bid submission start and end date, bid opening date, financial bid opening date, each marked with a [tender/milestones/title] and a due date [tender/milestones/dueDate |
| Milestone Type | tender/milestones/type | String | Published Date |
| Milestone Due Date | tender/milestones/dueDate | Datetime | Published Date |
| Document Download / Sale Start Date Milestone | tender/milestones/title | String | Document Download / Sale Start Date |
| Milestone Due Date | tender/milestones/dueDate | Datetime | Document Download / Sale Start Date |
| Clarification Start Date Milestone | tender/milestones/title | String | Clarification Start Date |
| Milestone Due Date | tender/milestones/dueDate | Datetime | Clarification Start Date |
| Bid Submission Start Date Milestone | tender/milestones/title | String | Bid Submission Start Date |
| Milestone Due Date | tender/milestones/dueDate | Datetime | Bid Submission Start Date |
| Bid Opening Date Milestone | tender/milestones/title | String | Bid Opening Date |
| Milestone Due Date | tender/milestones/dueDate | Datetime | Bid Opening Date |
| Document Download / Sale End Date Milestone | tender/milestones/title | String | Document Download / Sale End Date |
| Milestone Due Date | tender/milestones/dueDate | Datetime | Document Download / Sale End Date |
| Clarification End Date Milestone | tender/milestones/title | String | Clarification End Date |
| Milestone Due Date | tender/milestones/dueDate | Datetime | Clarification End Date |
| Bid Submission End Date Milestone | tender/milestones/title | String | Bid Submission End Date |
| Milestone Due Date | tender/milestones/dueDate | Datetime | Bid Submission End Date |
| Financial Bid Opening Date Milestone | tender/milestones/title | String | Financial Bid Opening Date |
| Milestone Due Date | tender/milestones/dueDate | Datetime | Financial Bid Opening Date |
| Corrigendum Description | tender/amendments/description | String | Details of any changes or amendments to the tender |
| Corrigendum Reason | tender/amendments/rationale | String | The rationale behind any changes or amendments |
| Published Date Amendment | tender/amendments/date | Datetime | Date of Amendment being Published |
| Bid Opening Place | tender/bidOpening/address/streetAddress | String | The address where bids will be opened |
<br>
Parties

| Title | Path | Data Type | Desc |
|-------|------|-----------|------|
| Organisation Chain ID | parties/id | String | The unique identifier for each organization involved in the tender |
| Organisation Chain Name | parties/name | String | The name of each organization involved in the tender |
| Organisation Chain Roles | parties/roles | String | Buyer / Tenderer / Procuring Entity |
| Name ID | parties/id | String | A unique identifier for individuals or entities involved in the tender |
| Name | parties/name | String | The name of individuals or entities involved in the tender |
| Address Street | parties/address/streetAddress | String | The street address of the party involved in the tender |
| Bidder ID | parties/id | String | The unique identifier for each bidder participating in the tender |
| Bidder Name | parties/name | String | The name of each bidder participating in the tender |
| Bid Number ID | parties/id | String | A unique number assigned to each bid submitted in the tender |
<br>
Bid and Award Details 

| Title | Path | Data Type | Desc |
|-------|------|-----------|------|
| Bid Number | bids/details/id | String | A unique identifier for each bid submitted |
| Bidder Name | bids/details/tenderers/name | String | The name of the entity or individual submitting the bid |
| Bidder Name ID | bids/details/tenderers/id | String | A unique identifier for each bidder |
| Submitted Date | bids/details/date | Datetime | The date on which the bid was submitted |
| Status | bids/details/status | String | The current status of the bid (e.g., pending, accepted, rejected, Financial Evaluation, Technical Evaluation, AOC) |
| Bid Number (Award) | awards/suppliers/id | String | The bid number associated with the award |
| Awards ID | awards/id | String | A unique identifier for each award given |
| Bidder Name (Award) | awards/suppliers/name | String | The name of the bidder who won the award |
| Awarded Currency | awards/value/currency | String | The currency in which the award value is denominated |
| Awarded Value | awards/value/amount | Float | The value of the award |
| Contract Date | awards/contractPeriod/startDate | Datetime | The start date of the contract associated with the award |
| Contract Value ID | statistics/id | String | A unique identifier related to the contract value |
| Work Completion Period (days) | awards/contractPeriod/durationInDays | Integer | The number of days allocated for the completion of the contract work |
| Calculated | buyer/id | String | The identifier for the buyer |
| Contract Value | statistics/value | Float | The total value of the contract |
| Contract Value Currency | statistics/currency | String | The currency in which the contract value is expressed |
| Type of Measure | statistics/measure | String | Type of Measure (ContractValue) |

