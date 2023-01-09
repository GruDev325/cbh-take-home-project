# Ticket Breakdown
We are a staffing company whose primary purpose is to book Agents at Shifts posted by Facilities on our platform. We're working on a new feature which will generate reports for our client Facilities containing info on how many hours each Agent worked in a given quarter by summing up every Shift they worked. Currently, this is how the process works:

- Data is saved in the database in the Facilities, Agents, and Shifts tables
- A function `getShiftsByFacility` is called with the Facility's id, returning all Shifts worked that quarter, including some metadata about the Agent assigned to each
- A function `generateReport` is then called with the list of Shifts. It converts them into a PDF which can be submitted by the Facility for compliance.

## You've been asked to work on a ticket. It reads:

**Currently, the id of each Agent on the reports we generate is their internal database id. We'd like to add the ability for Facilities to save their own custom ids for each Agent they work with and use that id when generating reports for them.**


Based on the information given, break this ticket down into 2-5 individual tickets to perform. Provide as much detail for each ticket as you can, including acceptance criteria, time/effort estimates, and implementation details. Feel free to make informed guesses about any unknown details - you can't guess "wrong".


You will be graded on the level of detail in each ticket, the clarity of the execution plan within and between tickets, and the intelligibility of your language. You don't need to be a native English speaker, but please proof-read your work.

## Your Breakdown Here
Ticket1.
Subject: Database Redesign
Acceptance criteria: Pk auto increment
Time/effort estimates: 0.5hr
Implementation details:
Add a new FacilityVSAgent Datatable.
This table contains the relation between Facilities and Agents.
This table has 4 fields: pk, Facility_ID, Agent_ID and custom ID.
Here Facility_ID, Agent_ID are same as pk of Facility Table and Agents Table respectively.
Custom ID is inputed by Facility Manager or Admin.
According to Facilites and Agents, we need to add some codes to make the custom ID unique.

Ticket2.
Subject: Add a new Function named getShiftsByFacilitywitCustomID
Acceptance criteria: Result list of shifts must contain metadata of Agents with Custom ID.
Time/effort estimates: 1hr
Implementation details:
Add a new function to get the list of shifts for a facility that contains the metadata about the Agent with the custom ID.


Ticket3.
Subject: Add a new Function named generateReportByCustomID
Acceptance criteria: Parameters: Facility ID, Custom ID
Time/effort estimates: 1hr
Implementation details:
This function returns the PDF report of a specific Agent with custom ID on a specific Facility.
