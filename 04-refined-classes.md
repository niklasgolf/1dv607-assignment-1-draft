# Task 1 - Refined Conceptual Classes

After looking at my candidate classes again, I decided that some of them represent important concepts in the domain, while others should be removed or combined with other concepts.

## Accepted Candidate Conceptual Classes

Tenant - Important because tenants make reservations, use laundry rooms and report faults.

Property Manager - Responsible for laundry rooms, maintenance and tenant-related problems.

Maintenance Technician - Responsible for repairing machines and recording maintenance work.

Housing Company - Manages the buildings and laundry facilities.

Apartment Building - Represents the buildings where the tenants live.

Laundry Room - An important physical place that tenants reserve and access.

Machine - Represents the equipment available in a laundry room.

Washing Machine - A specific type of machine.

Dryer - Another specific type of machine.

Reservation - Represents a booking made by a tenant.

Time Slot - Represents the period of time that can be reserved.

Fault Report - Records a problem with a machine or laundry room.

Maintenance - Represents maintenance work performed on a machine or laundry room.

Maintenance Schedule - Represents planned maintenance.

Maintenance History - Keeps information about previous maintenance.

Access Permission - Represents temporary permission to enter a laundry room.

Access Attempt - Records an attempt to enter a laundry room.

Notification - Represents information sent about reservations or faults.

## Discarded or Combined Candidates

Person - Too general. The important roles are Tenant, Property Manager and Maintenance Technician.

Insurance Company - It is an offstage actor and does not seem important enough for the main domain model.

Reservation History - I think this can be represented by keeping old Reservation objects instead of having a separate class.

Incident - Problems and damages can be handled through Fault Report, so I do not think this needs its own class.

Access Violation - This can be represented by an Access Attempt where access was denied, so I do not think it needs to be a separate class.

Reminder - A reminder is a type of Notification, so I combined these.

Reservation Limit - This seems more like a rule or value connected to reservations than a separate class.

Maintenance Priority - This seems more like information about a fault or maintenance than its own class.

Booking Priority - This is a rule and the requirements are also unclear about how it should work.

Apartment - The requirements mainly connect tenants to apartment buildings and laundry rooms. I do not think individual apartments are important enough for this model.

Laundry Facility - This overlaps with Laundry Room, so I kept Laundry Room.

Booking - This means approximately the same thing as Reservation, so I kept Reservation.

Laundry Time and Reserved Period - These are represented by Time Slot.

Active Reservation, Upcoming Reservation and Cancelled Reservation - These are different states of a Reservation rather than separate classes.

Machine Usage and Usage Statistics - These seem to be information calculated from reservations and machine usage rather than separate conceptual classes.

Authentication, Login Information, Username, Password and Credentials - These are connected to authentication and software implementation rather than the main problem domain.

System, Laundry Room Booking System, Database and Request - These describe the software system or implementation and are not real-world conceptual classes.

Booking Board, Digital Display, Confirmation and Error Message - These are related to how information is shown to users and are not important conceptual classes.

Key Tag and Mobile Access - These are ways of accessing the laundry room, but I do not think they need to be separate conceptual classes in my first model.
