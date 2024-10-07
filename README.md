This project aimed to address Special Emphasis Notice Area 1: Address health equity and social determinants of health through innovative, open-source technology tools, and electronic health records. 

1.	Understand and characterize the elements of a comprehensive care plan bridging the domains of need and services across both organizations, 
2.	Co-design and pilot test standards-based, open source, FHIR-enabled electronic interoperable care plan accessible to both institutions and the patient, and 
3.	Conduct a rigorous evaluation of the pilot approach to understand its impact on the and considerations for scaling across additional service domains and institutions.

The team designed a referral infrastructure system to support the “Aligning Housing and Healthcare” use cases between a community health center and a community-based organization (CBO), herein referred to as the eCare Plan. 

The attached deployment document details the setup of Azure Health Data Services (AHDS) and FHIR Services, the Azure Active Directory, and deployment of the CBO and Referral Handler Service applications. It also reviews the set up and hosting of the Referral Handler Service at a Fixed IP Address. Finally, it establishes the connection between the Referral Handler Service to Athena Practice (aP) for authentication and reading of FHIR data. It does not include documentation on the authentication and connection of the Referral Handler Service to AHDS and of the eCare Plan to AHDS. 
