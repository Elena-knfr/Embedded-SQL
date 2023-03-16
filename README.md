# Intro-to-DB (Postgres)


Working with a SQL schema for a database to manage waste collection for the City of Toronto.


Implemented Functions:

1. schedule_trip: Schedule a truck and two employees to a given route at a given date and time to pick up an unknown volume of waste. Both employees and the truck must not be scheduled for a different trip from 30 minutes before the expected start of the trip until 30 minutes after the expected end of this trip. The end of the trip can be computed by assuming that the truck travels an average of 5 kph. At least one of the employees must be able to drive the truck. Prefer employees with earlier hire dates and break ties by ascending eID.

2. schedule_trips: Schedule the given truck for trips on the given date using the following approach:
2.1 Find routes with no trips scheduled on the given date that have a waste type that the given truck is able to carry. Schedule trips on these routes in ascending order of their IDs.
2.2 Starting from 8 a.m., find the earliest available pair of drivers of whom at least one can drive the
given truck and both are available for the day. Break ties by choosing lower eIDs.
2.3 Continue scheduling trips, being sure to leave 30 minutes between trips using the assumption
that the truck will travel an average of 5 kph. The last trip must have ended by 4:00pm.

3. update_technicians: Use the given qualifications.txt file to update the database to reflect the new qualifications.

4. workmate_sphere: Good and bad habits get passed from worker to worker when they work together. For employee e1, any employee who has been on a trip with e1 is part of e1’s workmate sphere. Recursively, any employee who has been on a trip with an employee in e1’s workmate sphere is also in e1’s workmate sphere.

5. schedule_maintenance: For each truck with most recent maintenance over 90 days ago before the given date, schedule maintenance with a technician qualified to work on that truck. Choose the first day after the given date when there is a qualified technician available (not scheduled to maintain another truck that day) and the truck is not scheduled for a trip/maintenance. If there is more than one technician available on a given day, choose the one with the lowest eID.

6. reroute_waste: The given facility had an emergency shutdown. Reroute the trips scheduled on the given date to this Facility to another facility that takes the same type of waste. Don’t worry about too many trips arriving at the same time, each facility has ample receiving facility.
