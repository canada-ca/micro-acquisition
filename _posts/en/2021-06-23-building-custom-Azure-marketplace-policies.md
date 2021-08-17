---
layout: post
title: Building custom Azure marketplace policies
ref: opportunity1
lang: en
skills:  Azure Policies and Azure Runbooks (via Powershell)
value: $6,500 (excluding taxes)
closing_date: 2021-07-12T23:59:59-04:00
start_date: 2021-07-16
delivery_date: 2021-07-23T23:59:59-04:00
selected_bidder:
selected_bidder-link:
submitted_work-link:
last_modified: 2021-06-30
update: closing_date
short_desc: "Develop scripts to automatically set policies in Azure Marketplace/Private marketplace that will govern which 3rd party offerings are used by Employment and Social Development Canada (ESDC) clients."
---

## Description

### Background

The work in this opportunity is being requested by the Cloud Operations team at ESDC.

Cloud technologies are enabling transformation within government; improving service delivery to Canadians.
As part of the rollout of Cloud at ESDC, there are a number of Azure instances in use at ESDC.

These instances are using [a hub and spoke model](https://docs.microsoft.com/en-us/azure/architecture/reference-architectures/hybrid-networking/hub-spoke?tabs=cli) to group common services that are foundational to all cloud deployments.
The hub represents a set of common services that provide capabilities to spokes.

Each Azure client at ESDC is uniquely identified by an Azure Subscription or a Resource Group.
At the beginning the Spoke was implemented as a Resource Group but this is now being changed to use Management Groups and Subscriptions instead  as industry best practices.
ESDC clients on Azure instances can make use of Azure Marketplace 1st and 3rd party offerings.
The use of these offerings, like the use of Azure instances, is centrally managed at ESDC in collaboration with other government organizations to simplify administration and for security purposes.

Most of the 1st party offerings in the Marketplace are approved by default and ESDC clients can use them without further approvals.
3rd party offerings have to be approved by both the administrator and government organizations external to ESDC, before they are added to ESDC's Private Marketplace.
Currently 45 3rd party offerings have been approved via this process for ESDC Azure clients to use.
A sample of the approved 3rd party offerings includes *SendGrid, Fortinet FortiGate Next-Generation Firewall, Cisco Cloud Services Router (CSR) 1000V, CIS Ubuntu Linux 18.04 LTS Benchmark L1, etc.*.
A sample of the 3rd party offerings which have not been approved (and do not appear in the ESDC Private Marketplace) includes: VIAcode Managed Services for Azure, Nasuni Cloud File Services (NMC), Sycomp Storage Fueled by IBM Spectrum Scale, etc.

If an ESDC Azure client wants to use a 3rd party offering that is not yet approved (and so not in the Private Marketplace), the client is able to request that it be added.
This means the list of approved 3rd party offerings in the Private Marketplace will change over time.
If a 3rd party offering is approved for one ESDC client it is available for purchase by all ESDC clients – everyone sees the same Private marketplace.

If an ESDC Azure client wants to use a 3rd party offering in the Private Marketplace that has a ‘Price starts at’ >$0.00 they must seek financial approval for the funds to purchase that  3rd party offering.
Once an ESDC client has financial approval to purchase the 3rd party offering, a communication is sent to the Cloud Operations team from the client with the name of the 3rd party offering.
(Note: This communication is out of scope.)

This funding process leads us to the problem we need help to solve.
While built-in policies exist within Azure there are no policies to restrict clients from installing 3rd party offerings once they have been included in the Private Marketplace offerings.

### The work

To complete this opportunity, you must provide:

1. A script (or scripts) written in PowerShell which must:
   - Create a JSON file to implement a custom Azure policy that will prevent all ESDC Azure clients from installing any Marketplace (including the Private Marketplace) 3rd party offerings that have a ’Price starts at’ of >$0.00/hr.
   - Enable filtering which offerings are allowed or denied by Publisher, Offer, and  Plan. The filter should allow for wildcards.
   - Ensure that only those clients who receive financial approval to use an approved offering (in the Private Marketplace) are able to install that offering.
   - Prevent a client with a subscription who does not have financial approval to use an approved 3rd party offering, from installing that offering. If the client tries to install the offering they should receive the following message in English or French depending on the language of their UI:
     - English message: “You must seek financial approval to use this Azure Marketplace offering before you can install it.”
     - French message: " Vous devez demander l’approbation financière pour utiliser cette offre Azure Marketplace avant de pouvoir l'installer.”
2. Documentation (both in-line comments and a separate document) about what you are providing and how it works.  Ensure that your documentation/comments describes the logic and/or business rules used by your script or section of a script. Also, please use descriptive variable names and put spaces between large blocks of comments.

<hr/>

## Application evaluation

Your application will be evaluated using the following criterion:

1. Confirm that you have the skills to complete this work. Please provide a short, written statement (250 words or less, half a page) demonstrating how you have the required skills in  Azure Policies and Azure Runbooks (via Powershell). Describe when you gained these skills, what you did and how you did it. Examples could include: previous work experience, school work, Civic Tech projects etc.

You will also be required to confirm that you meet the following eligibility criteria:

- you have reached the age of majority and are contractually competent
  
AND

- you are Canadian, First Nations, Métis, Inuit or a permanent resident of Canada

OR

- you are a foreign worker/student and have the appropriate [work permit(s)](https://www.canada.ca/en/immigration-refugees-citizenship/services/work-canada/permit.html) to work in Canada.

## Work acceptance criteria

This is a fixed price opportunity governed by the terms of the Micro-Acquisition pilot. To be paid the fixed price, you must:

1. Deliver source code which fulfills all the requirements in the opportunity description above.  In addition:

   - The code must be delivered with an MIT license
   - The code must  pass the following tests:
     - [PowerShell Script Analyzer](https://github.com/PowerShell/PSScriptAnalyzer) - all default rules (all warnings, alerts and suppressions of those warnings or alerts in code must be included in the documentation along with a justification)
     - The winning supplier will be given access to an unsecured sandbox on Azure in order to do the following functional tests to ensure the scripts are working:
       - A client with a subscription that has financial approval for approved 3rd party offering: ‘ CIS Microsoft Windows Server 2016 Benchmark L1’ in the private marketplace can pass validation to install it.
       - A client with a subscription that does NOT have financial approval for approved 3rd party offering ‘ CIS Microsoft Windows Server 2016 Benchmark L2’ in the private marketplace will fail validation when trying to install this approved 3rd party offering.
       - A client with a subscription that has financial approval for approved 3rd party offering: ‘ CIS Microsoft Windows Server 2008 R2 Benchmark L1’ in the private marketplace cannot pass validation to install approved 3rd party offering: ‘Secure VPN Server’, as they don’t have financial approval for this offering.
       - A client with a subscription that does not have financial approval for any 3rd party offering cannot pass validation to install any 3rd party offering in the private marketplace.
       - If a third party offering becomes approved for all ESDC Azure subscriptions and is added to the Private Marketplace, clients are immediately prevented from passing validation to install it until they have financial approval.

*Note that the sandbox will be pre-populated with subscriptions and some offerings in the Private marketplace.*
