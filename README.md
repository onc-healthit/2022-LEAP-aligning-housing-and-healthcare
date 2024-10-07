This project aimed to address Special Emphasis Notice Area 1: Address health equity and social determinants of health through innovative, open-source technology tools, and electronic health records. 

1.	Understand and characterize the elements of a comprehensive care plan bridging the domains of need and services across both organizations, 
2.	Co-design and pilot test standards-based, open source, FHIR-enabled electronic interoperable care plan accessible to both institutions and the patient, and 
3.	Conduct a rigorous evaluation of the pilot approach to understand its impact on the and considerations for scaling across additional service domains and institutions.

The team designed a referral infrastructure system to support the “Aligning Housing and Healthcare” use cases between a community health center and a community-based organization (CBO), herein referred to as the eCare Plan. 

This document details the setup of Azure Health Data Services (AHDS) and FHIR Services, the Azure Active Directory, and deployment of the CBO and Referral Handler Service applications. It also reviews the set up and hosting of the Referral Handler Service at a Fixed IP Address. Finally, it establishes the connection between the Referral Handler Service to Athena Practice (aP) for authentication and reading of FHIR data. It does not include documentation on the authentication and connection of the Referral Handler Service to AHDS and of the eCare Plan to AHDS. 

Architecture Diagram
The following is an architecture diagram (Figure 1) of the entire referral infrastructure system. Here is a short description of each component:

•	Athena Practice EHR: This is the EHR system that Community Health Center (CHC) uses. It has FHIR R4 API endpoints to expose certain FHIR Resources to external, authorized and authenticated entities. CHC users include clinicians and care coordinators.
•	Referral Handler Service: This is a stateless backend service that is hosted on the Azure secure cloud environment. It is hosted at a fixed IP address using an API management service. The IP has been whitelisted by athenaPractice. It is capable of querying and receiving FHIR payloads and saving it to a FHIR data store.
•	Azure API Management Service: An Azure service to manage APIs in a cloud environment. Azure API Management Service has a Static IP, which is whitelisted and is used to manage the APIs for requesting access and query the FHIR Resources from Athena Practice EHR.
•	Social Care Hub/ Azure Health Data Services (AHDS): Azure Health Data Services is a cloud based FHIR data store hosted in the Azure environment. The project has called this data store the “Social Care Hub”. This is where data authored by the eCare Plan is stored.
•	Backend Services: This is the backend service for the eCare Plan. It performs operations such as querying, creating, saving, and updating FHIR resources in the Social Care Hub.
•	eCare Plan: The eCare Plan is the user-facing application that allows both the community-based organization and CHC users to see and interact with the Referral information stored in the Social Care Hub.
•	Azure Active Directory: Azure Active Directory (recently renamed “Microsoft Entra ID”) is a cloud-based identity and access management solution. CBO and CHC users who should have access to the eCare Plan are added by the Azure administrator to the Azure Active Directory. The users use an email and password which is validated by Azure AD to get access to the eCare Plan.

Figure 1 AC LEAP Architecture Master Diagram


