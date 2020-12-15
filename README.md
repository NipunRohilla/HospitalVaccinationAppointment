Business statement: As a cautious action after Covid-19, VaccNow is an healthcare organization managing the process of Covid-19 vaccine to public,
so that the VaccNow is planning to build multi their digital channels for consuming a modern API for basic features. This is
planned to be API first approach, of well-tested functions and enabling agility of later modifications.
▪ At the digital factory, we currently have a microservices architecture with services mostly written in Spring Boot.
▪ We would like you to develop a single service using Spring Boot with either Java or Kotlin that exposes several REST
endpoints (see next page)
▪ You can use whatever database and data access method; the application should create the required database structure.
▪ You should include a README file that has instructions for us to get the solution running on our machines

1.This spring boot application is using java8, spring boot, spring REST, H2 db and flyway library for db management.

2.It consists of .sql file which gets executed at the time of start of application.

3. Sql files has create and INSERT queries.

4. H2 properties have been specified in application properties file. 
Also username = 'user' and 
password= 'password'

Given the time constraint, Following assumptions are being made for the program as below:
1. There is no provision to cancel the time slot.
2. By default the status will be "OPEN".
3. each time a time slot is booked, "RESERVED" status is assigned to status field of Branch_Schedule_tb table.
4. Doctors availability arrangement will be taken care by hospital management as it is not defined in exercise.
5. TO make it simpler, Adding data of availability schedule of 2 branches for a week only.
6. Once patient visits hospital for vaccination, All the applied vaccination will have status "USED" in BranhSchedule table wrt to patient.


------------------------

Steps to execute the program:
1. mvn clean package
2. mvn spring-boot:run
3. Execute below urls to get the REST api response:

▪ Get a list of all branches
http://localhost:8080/allBranch

▪ Get a list of all available vaccines per branch
http://localhost:8080/availableVaccines

▪ Get a specific availability by branch
http://localhost:8080/getSpecificScheduleByBranch/{branchId}/{dateTime}
Eg:
http://localhost:8080/getSpecificScheduleByBranch/1/2020-12-15T10:15

▪ Get available time for a branch
http://localhost:8080/getAvailableTimeByBranch/{branchId}
Eg:
http://localhost:8080/getAvailableTimeByBranch/1


▪ Schedule vaccination timeslot (15 minutes)
http://localhost:8080/scheduleTimeSlot/{branchId}/{dateTime}
Eg:
http://localhost:8080/scheduleTimeSlot/1/2020-12-15T12:45:00


▪Get a list of all applied vaccination per branch
http://localhost:8080/allAppliedVaccinationByBranch/{branchId}
eg:
http://localhost:8080/allAppliedVaccinationByBranch/1

▪ Get a list of all applied vaccination per day/period
http://localhost:8080/allAppliedVaccinationPerDay/{dateTime}
eg:
http://localhost:8080/allAppliedVaccinationPerDay/2020-12-15T09:45:00

▪ Show all confirmed vaccinations over a time period
http://localhost:8080/allConfirmedVaccinationOverPeriod/{fromDateTime}/{toDateTime}
eg:
http://localhost:8080/allConfirmedVaccinationOverPeriod/2020-12-15T09:45:00/2020-12-16T18:45:00
