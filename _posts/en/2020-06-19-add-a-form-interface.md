---
layout: post
# title: Fix accessibility issues in Rocket.Chat
title: Building a form interface to collect micro-acquisition applications
ref: opportunity1
lang: en
skills: Javascript/Typescript
value: $0,000
closing_date: 2020-10-20T23:59:59-07:00
start_date: 2020-11-01
delivery_date: 2020-11-15T23:59:59-07:00
selected_bidder:
selected_bidder-link:
submitted_work-link:
last_modified: 2020-09-24
# short_desc: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam venenatis tincidunt ipsum et vulputate. Nunc ultricies, diam eget blandit ornare, purus libero dapibus turpis, vel faucibus felis est sed libero. In et erat in mi ultrices dapibus."
short_desc: "Help make the Micro-acquisition process easier for suppliers by building a form interface suppliers will use to submit applications. This form interface will replace the existing process of email submission."
---

## Description

### Background

<!-- Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam venenatis tincidunt ipsum et vulputate. Nunc ultricies, diam eget blandit ornare, purus libero dapibus turpis, vel faucibus felis est sed libero. In et erat in mi ultrices dapibus.

Interdum et malesuada fames ac ante ipsum primis in faucibus. Sed vitae tellus a erat efficitur posuere in efficitur lorem. Maecenas accumsan fringilla odio, quis aliquam est suscipit at. Nulla viverra lectus sed tortor imperdiet porttitor. Etiam sed tempus magna, non pulvinar mauris. Sed ultricies pharetra nibh nec gravida. Phasellus fringilla justo in semper finibus. Vestibulum eget nibh nec erat pharetra iaculis. In porta ipsum ac libero varius, vel condimentum metus vestibulum. Fusce scelerisque ut diam nec pulvinar. Aenean ipsum risus, sagittis sed euismod semper, varius eget augue. Mauris nec mi tincidunt, fringilla diam non, vulputate velit. Aenean in nunc turpis. Ut rutrum vehicula diam nec mattis. -->
In order to deploy the micro-acquisition pilot rapidly and easily, a low tech solution and process was chosen for suppliers to submit their applications.  This process involves suppliers sending their application for a micro-acquisition opportunity in the body of an email to a generic email inbox.

Within the application suppliers:

1. Must certify that they are Canadian and/or First Nations, Métis or Inuit OR that they have work permits to work in Canada.

2. Are asked to voluntarily provide some demographic information about themselves

Once bids are received they are manually anonymized and consolidated into a single file so that they can be sent on to the ESDC client for evaluation once the submission deadline has passed.

Demographic information that is voluntarily submitted is also anonymized and stored to be used to determine the success of the pilot

The challenges with the current process:

1. No validation on the supplier’s application.  This means there is a high likelihood for mistakes. If a supplier forgets to include the text certifying ‘Canadian and/or....’ or includes the wrong text, their application will be rejected but only once the deadline has passed.  Validation cannot be manually done on applications as applications could come in minutes before the deadline and that would not give us time to write back (via email) to say, you have forgotten something.

2. Suppliers will be less likely to provide demographic information about themselves in the email as they will have to type or copy/paste the text into an email (they do not have the option to simply select checkboxes with the current process).

3. If the demand for the micro-acquisition pilot is high and we get 1000+ applications for an opportunity, the existing manual process is not sustainable.

### Opportunity

<!-- Nam tincidunt suscipit magna a consequat. Fusce scelerisque erat nec nisl mollis aliquam. Integer quis risus cursus, laoreet enim non, vestibulum lorem. Sed non erat at mauris posuere ornare ut quis arcu. In at velit placerat, vehicula diam nec, scelerisque odio. Proin vel mi lobortis, malesuada neque fermentum, bibendum erat. Mauris ac erat a mauris ornare aliquet aliquam eget sapien. Mauris vel diam volutpat, ornare massa sed, porta justo. Etiam euismod nibh eget sapien dictum, ac commodo tellus interdum. Proin pretium lectus enim, eu tempus risus maximus sit amet. Nam blandit, massa eu vehicula ultricies, augue ex scelerisque nibh, sit amet varius lorem lacus non mi. Quisque auctor efficitur enim.

Nullam sed venenatis erat, sed fringilla odio. Vivamus lacinia feugiat scelerisque. Donec vestibulum rutrum nunc, eget finibus augue. Morbi laoreet dapibus purus, sed euismod elit tristique eget. Vestibulum sed nulla iaculis, tempus ante a, commodo erat. Aenean vitae sem scelerisque risus bibendum bibendum et semper tellus. Maecenas eget malesuada tellus. -->
To complete this opportunity you must provide:

- Add a web form to the MA website that requests the applicant the following:

  - (free text, max 500 chars) Justification of skills. This is mandatory.

  - (checkbox) statement about belonging to eligible groups (Canadians, First Nations, etc.). This is mandatory.

  - Optional demographic questions as follows:

    - (Yes/No) Have you worked for the GC before in any capacity? (student, contract, part-time, full-time)

    - (Yes/No) Have you been part of a GC procurement process before (for a contract rather than a job)

    - (free text, max 100 chars) Where do you reside? (Province/Community, country)

    - (number) If you are applying as a company, how many employees does your company have?

- The form will send the data via email using an ESDC SMTP server.

- After successful submission of the form, a confirmation web page is displayed to the end-user “thank you for applying to a micro-acquisition opportunity”.

- If the submission of the form is not successful (e.g. if some mandatory fields are missing) this message should be displayed “Please fill in the <field name> field”.

- The submitted form application must also meet the following non-functional requirements:

  - Accessibility

  - Official languages (supports switching languages, don’t need to provide the French/English content itself)
  
- Documentation (either in-line comments or as a separate document) about what you are providing and how it works.  Ensure that your documentation/comments describes the logic and/or business rules used by your script or section of a script. Also, please use descriptive variable names and put spaces between large blocks of comments.

<hr/>

## Acceptance Criteria

<!-- Nullam sed venenatis erat, sed fringilla odio. Vivamus lacinia feugiat scelerisque. Donec vestibulum rutrum nunc, eget finibus augue. Morbi laoreet dapibus purus, sed euismod elit tristique eget. Vestibulum sed nulla iaculis, tempus ante a, commodo erat. Aenean vitae sem scelerisque risus bibendum bibendum et semper tellus. Maecenas eget malesuada tellus.

1. criteria 1
2. criteria 2
3. criteria 3 -->

This is a fixed price opportunity governed by the terms of the Micro-Acquisition pilot. To be paid the fixed price, you must meet all of the following criteria:

1. The code must be delivered with an MIT license

2. A reviewed and approved pull request that adds source code to fulfill all the requirements in the opportunity description

3. The code must pass the following automated tests:

- [https://www.deque.com/axe/auditor/](https://www.deque.com/axe/auditor/ )

- JavaScript lint CLI [https://www.npmjs.com/package/jslint-cli](https://www.npmjs.com/package/jslint-cli)

## Proposal Evaluation Criteria

<!-- Nullam sed venenatis erat, sed fringilla odio. Vivamus lacinia feugiat scelerisque. Donec vestibulum rutrum nunc, eget finibus augue. Morbi laoreet dapibus purus, sed euismod elit tristique eget. Vestibulum sed nulla iaculis, tempus ante a, commodo erat. Aenean vitae sem scelerisque risus bibendum bibendum et semper tellus. Maecenas eget malesuada tellus.

1. criteria 1
2. criteria 2
3. criteria 3 -->

Your proposal will be evaluated using the following criterion:

1. Confirm that you have the skills to complete this work. Please provide a short, written statement (250 words or less, half a page) demonstrating how you have the required skills in Javascript or Typescript. Describe when you gained these skills, what you did and how you did it. Examples could include: previous work experience, school work, Civic Tech projects etc.

You  will also be required to confirm that you meet either of the following eligibility criteria:

- you are a Canadian citizen and/or are First Nations, Métis or Inuit, or

- you have the appropriate work permits to work in Canada.
