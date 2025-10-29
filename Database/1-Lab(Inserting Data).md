DROP TABLE IF EXISTS Lesson_Attendance CASCADE; DROP TABLE IF EXISTS
Student_Plan CASCADE; DROP TABLE IF EXISTS StudentPerformance CASCADE;
DROP TABLE IF EXISTS Course_Dependenc CASCADE; DROP TABLE IF EXISTS
Lesson_Replacment CASCADE; DROP TABLE IF EXISTS WorkStation CASCADE;
DROP TABLE IF EXISTS Equipment CASCADE; DROP TABLE IF EXISTS
Type_equipment CASCADE; DROP TABLE IF EXISTS Classroom CASCADE; DROP
TABLE IF EXISTS Building CASCADE; DROP TABLE IF EXISTS Lesson_Reason
CASCADE; DROP TABLE IF EXISTS CourseTheme CASCADE; DROP TABLE IF EXISTS
Student CASCADE; DROP TABLE IF EXISTS Course CASCADE; DROP TABLE IF
EXISTS Category CASCADE; DROP TABLE IF EXISTS Lesson CASCADE; DROP TABLE
IF EXISTS Teacher_Direction CASCADE; DROP TABLE IF EXISTS Direction
CASCADE; DROP TABLE IF EXISTS Teacher CASCADE; DROP TABLE IF EXISTS
Country CASCADE; DROP TABLE IF EXISTS Status CASCADE; \--1 CREATE TABLE
Country ( CountryID SERIAL, Name VARCHAR(100), ShortName VARCHAR(30),
CodeNumber VARCHAR(20), Description TEXT );

\--2 CREATE TABLE Teacher ( TeacherID SERIAL, LastName VARCHAR(100),
FirstName VARCHAR(100), MiddleName VARCHAR(100), BirthDate DATE, Phone
VARCHAR(20), Address TEXT, Email VARCHAR(100), CountryID INT );

\--3 CREATE TABLE Direction ( DirectionID SERIAL, Name VARCHAR(100) );

\--4 CREATE TABLE Teacher_Direction (

DirectionID SERIAL, TeacherID SERIAL );

\--5 CREATE TABLE Lesson ( LessonID SERIAL, Date DATE, Name
VARCHAR(100), Status VARCHAR(50), onlinclassname VARCHAR(100),
LinktoClass VARCHAR(200), Descrip_Online TEXT, TeacherID SERIAL, ThemeID
SERIAL, ReasonID SERIAL, ClassroomID SERIAL, ReplacementID SERIAL );

\--6 CREATE TABLE Course ( CourseID SERIAL, Name VARCHAR(100),
Description TEXT, StartingDate DATE, EndingDate DATE, CategoryID SERIAL,
DependenceID SERIAL );

\--7 CREATE TABLE CourseTheme ( ThemeID SERIAL, Name VARCHAR(100),
Description TEXT, CourseID SERIAL );

\--8 CREATE TABLE Category ( CategoryID SERIAL, Name VARCHAR(100),
Description TEXT );

\--9 CREATE TABLE Student ( StudentID SERIAL, FirstName VARCHAR(100),
SecondName VARCHAR(100), NikeName VARCHAR(100), Phone VARCHAR(20),
Address VARCHAR(200), Email VARCHAR(100), AdmissionDate DATE,
Description TEXT, CountryID SERIAL );

\--10 CREATE TABLE StudentPerformance ( StudentCourse SERIAL, Marks
INTEGER, status_id SERIAL, CourseID SERIAL, StudentID SERIAL );

\--11 CREATE TABLE Student_Plan ( Stud_PlanID SERIAL, Planned_Start
DATE, Planned_Finish DATE, CourseID SERIAL, StudentID SERIAL );

\--12 CREATE TABLE Lesson_Reason ( ReasonID SERIAL, Description TEXT );

\--13 CREATE TABLE Building ( BuildingID SERIAL, Name VARCHAR(100),
Address VARCHAR(200), Description TEXT );

\--14 CREATE TABLE Classroom ( ClassroomID SERIAL, Name VARCHAR(100),
Number VARCHAR(20), Description TEXT, BuildingID SERIAL );

\--15 CREATE TABLE Equipment ( EquipmentID SERIAL, ClassroomID SERIAL,
Name VARCHAR(100), InventoryNumber VARCHAR(50), InstallationDate DATE,
Description TEXT, typeID SERIAL );

\--16 CREATE TABLE WorkStation ( WorkStationID SERIAL, ClassroomID
SERIAL, Name VARCHAR(100), Number VARCHAR(50), Address VARCHAR(200),
Description TEXT );

\--17 CREATE TABLE Course_Dependenc ( DependencID SERIAL, Description
TEXT, CourseID SERIAL );

\--18 CREATE TABLE Lesson_Attendance ( AttendanceID SERIAL, status
VARCHAR(50), Comments TEXT, Description TEXT, LessonID SERIAL, StudentID
SERIAL );

\--19 CREATE TABLE Type_equipment ( typeID SERIAL, Name VARCHAR(100),
registerNumber VARCHAR(50), ShortName VARCHAR(50) );

\--20 CREATE TABLE Status ( status_id SERIAL, Name VARCHAR(50),
Discription TEXT ); \--21 CREATE TABLE Lesson_Replacment ( ReplacementID
SERIAL, Reason VARCHAR(200), RescedualDate DATE );

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Now
the limitation will be
added\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\-\-\-\-\-\-\-\-\-\-\-\-\-- This section is only for the Primary Keys
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-- \--Country 1 ALTER
TABLE Country ADD CONSTRAINT pk_country PRIMARY KEY (CountryID);
\--Teacher 2 ALTER TABLE Teacher ADD CONSTRAINT pk_teacher PRIMARY KEY
(TeacherID); \--Direction 3 ALTER TABLE Direction ADD CONSTRAINT
pk_direction PRIMARY KEY (DirectionID); \--Teacher_Direction 4 ALTER
TABLE Teacher_Direction ADD CONSTRAINT pk_teacher_direction PRIMARY KEY
(DirectionID, TeacherID); \--Lesson 5 ALTER TABLE Lesson ADD CONSTRAINT
pk_lesson PRIMARY KEY (LessonID); \-- Course 6 ALTER TABLE Course ADD
CONSTRAINT pk_course PRIMARY KEY (CourseID); \--CourseTheme 7 ALTER
TABLE CourseTheme ADD CONSTRAINT pk_course_theme PRIMARY KEY (ThemeID);
\--Category 8 ALTER TABLE Category ADD CONSTRAINT pk_category PRIMARY
KEY (CategoryID); \--Student 9 ALTER TABLE Student ADD CONSTRAINT
pk_student PRIMARY KEY (StudentID); \--StudentPerformance 10 ALTER TABLE
StudentPerformance ADD CONSTRAINT pk_student_course PRIMARY KEY
(StudentCourse); \--Student_Plan 11 ALTER TABLE Student_Plan ADD
CONSTRAINT pk_student_plan PRIMARY KEY (Stud_PlanID); \-- Lesson_Reason
12 ALTER TABLE Lesson_Reason ADD CONSTRAINT pk_lesson_reason PRIMARY KEY
(ReasonID); \--Building 13 ALTER TABLE Building ADD CONSTRAINT
pk_building PRIMARY KEY (BuildingID); \--Classroom 14 ALTER TABLE
Classroom ADD CONSTRAINT pk_classroom PRIMARY KEY (ClassroomID);
\--Equipment 15 ALTER TABLE Equipment ADD CONSTRAINT pk_equipment
PRIMARY KEY (EquipmentID); \--WorkStation 16 ALTER TABLE WorkStation ADD
CONSTRAINT pk_workstation PRIMARY KEY (WorkStationID);
\--Course_Dependenc 17 ALTER TABLE Course_Dependenc ADD CONSTRAINT
pk_course_dependenc PRIMARY KEY (DependencID); \--Lesson_Attendance 18
ALTER TABLE Lesson_Attendance ADD CONSTRAINT pk_lesson_attendance
PRIMARY KEY (AttendanceID); \--Type_equipment 19 ALTER TABLE
Type_equipment ADD CONSTRAINT pk_type_equipment PRIMARY KEY (typeID);
\-- Status 20 ALTER TABLE Status ADD CONSTRAINT pk_status PRIMARY KEY
(status_id); \-- Lesson_Replacment 21 ALTER TABLE Lesson_Replacment ADD
CONSTRAINT pk_lesson_replacment PRIMARY KEY (ReplacementID);
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
This Section is for the Foreign Key
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
\--Country 1 ALTER TABLE Country ALTER COLUMN Name SET NOT NULL, ALTER
COLUMN ShortName SET NOT NULL, ALTER COLUMN CodeNumber SET NOT NULL;

\--Teacher 2 ALTER TABLE Teacher ALTER COLUMN LastName SET NOT NULL,
ALTER COLUMN FirstName SET NOT NULL, ALTER COLUMN BirthDate SET NOT
NULL, ALTER COLUMN Phone SET NOT NULL, ADD CONSTRAINT fk_teacher_country
FOREIGN KEY (CountryID) REFERENCES Country(CountryID);

\--Direction 3 ALTER TABLE Direction ALTER COLUMN Name SET NOT NULL;

\-- Teacher_Direction 4 ALTER TABLE Teacher_Direction ADD CONSTRAINT
fk_teacher_direction_direction FOREIGN KEY (DirectionID) REFERENCES
Direction(DirectionID), ADD CONSTRAINT fk_teacher_direction_teacher
FOREIGN KEY (TeacherID) REFERENCES Teacher(TeacherID);

\-- Lesson 5 ALTER TABLE Lesson ALTER COLUMN Date SET NOT NULL, ALTER
COLUMN Name SET NOT NULL, ADD CONSTRAINT fk_lesson_teacher FOREIGN KEY
(TeacherID) REFERENCES Teacher(TeacherID), ADD CONSTRAINT
fk_lesson_theme FOREIGN KEY (ThemeID) REFERENCES CourseTheme(ThemeID),
ADD CONSTRAINT fk_lesson_reason FOREIGN KEY (ReasonID) REFERENCES
Lesson_Reason(ReasonID), ADD CONSTRAINT fk_lesson_classroom FOREIGN KEY
(ClassroomID) REFERENCES Classroom(ClassroomID), ADD CONSTRAINT
fk_lesson_replacement FOREIGN KEY (ReplacementID) REFERENCES
Lesson_Replacment(ReplacementID);

\-- Course 6 ALTER TABLE Course ALTER COLUMN Name SET NOT NULL, ALTER
COLUMN EndingDate SET NOT NULL, ADD CONSTRAINT fk_course_category
FOREIGN KEY (CategoryID) REFERENCES Category(CategoryID), ADD CONSTRAINT
fk_course_dependence FOREIGN KEY (DependenceID) REFERENCES
Course_Dependenc(DependencID);

\-- CourseTheme 7 ALTER TABLE CourseTheme ALTER COLUMN Name SET NOT
NULL, ADD CONSTRAINT fk_course_theme_course FOREIGN KEY (CourseID)
REFERENCES Course(CourseID);

\-- Category 8 ALTER TABLE Category ALTER COLUMN Name SET NOT NULL;

\-- Student 9 ALTER TABLE Student ALTER COLUMN FirstName SET NOT NULL,
ADD CONSTRAINT fk_student_country FOREIGN KEY (CountryID) REFERENCES
Country(CountryID);

\--StudentCourse or StudentPerformance 10 ALTER TABLE StudentPerformance
ADD CONSTRAINT fk_student_course_status FOREIGN KEY (status_id)
REFERENCES Status(status_id), ADD CONSTRAINT fk_student_course_course
FOREIGN KEY (CourseID) REFERENCES Course(CourseID), ADD CONSTRAINT
fk_student_course_student FOREIGN KEY (StudentID) REFERENCES
Student(StudentID);

\-- Student_Plan 11 ALTER TABLE Student_Plan ALTER COLUMN Planned_Start
SET NOT NULL, ALTER COLUMN Planned_Finish SET NOT NULL, ADD CONSTRAINT
fk_student_plan_course FOREIGN KEY (CourseID) REFERENCES
Course(CourseID), ADD CONSTRAINT fk_student_plan_student FOREIGN KEY
(StudentID) REFERENCES Student(StudentID);

\-- Building 13 ALTER TABLE Building ALTER COLUMN Name SET NOT NULL,
ALTER COLUMN Address SET NOT NULL;

\-- Classroom 14 ALTER TABLE Classroom ALTER COLUMN Number SET NOT NULL,
ADD CONSTRAINT fk_classroom_building FOREIGN KEY (BuildingID) REFERENCES
Building(BuildingID);

\-- Equipment 15 ALTER TABLE Equipment ALTER COLUMN Name SET NOT NULL,
ALTER COLUMN InventoryNumber SET NOT NULL, ADD CONSTRAINT
fk_equipment_classroom FOREIGN KEY (ClassroomID) REFERENCES
Classroom(ClassroomID), ADD CONSTRAINT fk_equipment_type FOREIGN KEY
(typeID) REFERENCES Type_equipment(typeID);

\-- WorkStation 16 ALTER TABLE WorkStation ALTER COLUMN Name SET NOT
NULL, ALTER COLUMN Number SET NOT NULL, ADD CONSTRAINT
fk_workstation_classroom FOREIGN KEY (ClassroomID) REFERENCES
Classroom(ClassroomID);

\-- Course_Dependenc 17 \--Here is the question that how we are giveing
the foreign key here, Now \--we have selected the foreigen key for the
table as the \--CourseID (this is located in the Course table, however
we have the foreign key \--of this table in the course table already).
ALTER TABLE Course_Dependenc ADD CONSTRAINT fk_course_dependenc_course
FOREIGN KEY (CourseID) REFERENCES Course(CourseID);

\-- Lesson_Attendance 18 ALTER TABLE Lesson_Attendance ALTER COLUMN
status SET NOT NULL, ADD CONSTRAINT fk_lesson_attendance_lesson FOREIGN
KEY (LessonID) REFERENCES Lesson(LessonID), ADD CONSTRAINT
fk_lesson_attendance_student FOREIGN KEY (StudentID) REFERENCES
Student(StudentID);

\-- Type_equipment 19 ALTER TABLE Type_equipment ALTER COLUMN Name SET
NOT NULL, ALTER COLUMN registerNumber SET NOT NULL;

\-- Status 20 ALTER TABLE Status ALTER COLUMN Name SET NOT NULL;

\-- Lesson_Replacment 21 ALTER TABLE Lesson_Replacment ALTER COLUMN
Reason SET NOT NULL, ALTER COLUMN RescedualDate SET NOT NULL;

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Country \-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
INSERT INTO Country (Name, ShortName, CodeNumber, Description) VALUES
(\'Afghanistan\', \'AFG\', \'093\', \'My native birth land\');

INSERT INTO Country (Name, ShortName, CodeNumber, Description) VALUES
(\'Russia\', \'RU\', \'079\', \'The beautiful country\');

INSERT INTO Country (Name, ShortName, CodeNumber, Description) VALUES
(\'United Kingdom\', \'UK\', 0089,\'One of the beautiful land\');

INSERT INTO Country (Name, ShortName, CodeNumber, Description) VALUES
(\'Canada\', \'CA\', 001,\'One of the coldest land in world\'),
(\'United States\', \'USA\', \'002\', \'North American country\'),
(\'Germany\', \'DE\', \'049\', \'European country\'), (\'France\',
\'FR\', \'033\', \'Western European country\');

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into
Teacher\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
INSERT INTO Teacher (LastName, FirstName, MiddleName, BirthDate, Phone,
Address,Email, CountryID) VALUES
(\'Mia\',\'Muzamil\',\'\',\'2000-2-23\',\'+79539342355\',\'Voronezh,Russia\',\'daf@gmail.com\',(SELECT
CountryID FROM Country WHERE ShortName=\'AFG\'));

INSERT INTO Teacher (LastName, FirstName, MiddleName, BirthDate, Phone,
Address, Email, CountryID) VALUES (\'Oleg\',\'Alekcy\',\'Alekcyevich\',
\'1990-1-15\',\'+72343242366\', \'Moscow\', \'aksdf@gmail.com\',(SELECT
CountryID FROM Country WHERE ShortName=\'RU\'));

INSERT INTO Teacher (LastName, FirstName, MiddleName, BirthDate, Phone,
Address, Email, CountryID) VALUES
(\'Liam\',\'Donald\',\'Jan\',\'1934-4-23\',\'+42341313411\',\'New
York\', \'myna@mail.com\',(SELECT CountryID FROM Country WHERE
ShortName=\'US\'));

INSERT INTO Teacher (LastName, FirstName, MiddleName, BirthDate, Phone,
Address, Email, CountryID)VALUES (\'Khan\',
\'Mahmmod\',\'\',\'2003-2-23\',\'+931245533522\',\'Kandahar\',
\'khan@gmail.com\',(SELECT CountryID FROM Country WHERE
ShortName=\'AFG\'));

INSERT INTO Teacher (LastName, FirstName, MiddleName, BirthDate, Phone,
Address, Email, CountryID ) VALUES (\'Nasrat\',\'Rasool\',\'Sahib\',
\'1987-6-23\',\'+12345235322\',\'Ontario\',\'rasool@mail.com\',(SELECT
CountryID FROM Country WHERE ShortName=\'CA\'));

INSERT INTO Teacher (LastName, FirstName, MiddleName, BirthDate, Phone,
Address, Email, CountryID) VALUES
(\'Laura\',\'Josep\',\'Josee\',\'1942-9-14\',\'+43452436642\',\'Las
Vegas\', \'joshe@mail.com\',(SELECT CountryID FROM Country WHERE
ShortName=\'US\'));

\--SELECT\*FROM Teacher INNER JOIN Country ON
Teacher.CountryID=Country.CountryID ORDER BY TeacherID ASC;

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Direction
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-- INSERT
INTO Direction (Name) VALUES (\'Artificial Intelligence\'); INSERT INTO
Direction (Name) VALUES (\'Software Engineering\'); INSERT INTO
Direction (Name) VALUES (\'Computer Systems\'); INSERT INTO Direction
(Name) VALUES (\'Network and Security\'); INSERT INTO Direction (Name)
VALUES (\'Data Science\'); INSERT INTO Direction (Name) VALUES (\'Cyber
Security\');

SELECT \'Names\', Direction.Name FROM Direction;
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Teacher_Direction \-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

INSERT INTO Teacher_Direction (DirectionID,TeacherID) VALUES ((SELECT
DirectionID FROM Direction WHERE Name=\'Computer Systems\'),(SELECT
TeacherID FROM Teacher WHERE LastName=\'Mia\' AND
FirstName=\'Muzamil\'));

INSERT INTO Teacher_Direction (DirectionID, TeacherID) VALUES ((SELECT
DirectionID FROM Direction WHERE Name=\'Cyber Security\'),(SELECT
TeacherID FROM Teacher WHERE LastName=\'Laura\' AND
FirstName=\'Josep\'));

INSERT INTO Teacher_Direction (DirectionID, TeacherID) VALUES ((SELECT
DirectionID FROM Direction WHERE Name=\'Cyber Security\'),(SELECT
TeacherID FROM Teacher WHERE LastName=\'Nasrat\' AND
FirstName=\'Rasool\'));

INSERT INTO Teacher_Direction (DirectionID, TeacherID) VALUES ((SELECT
DirectionID FROM Direction WHERE Name=\'Software Engineering\'), (SELECT
TeacherID FROM Teacher WHERE LastName=\'Khan\' AND
FirstName=\'Mahmmod\'));

\--SELECT\*FROM Teacher_Direction;

\-- SELECT\*FROM Teacher INNER JOIN Teacher_Direction ON
Teacher.TeacherID=Teacher_Direction.TeacherID \-- INNER JOIN Direction
ON Direction.DirectionID=Teacher_Direction.DirectionID ; \--INNER JOIN
Country ON Country.CountryID=Teacher.TeacherID;

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Lesson_Reason
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-- INSERT
INTO Lesson_Reason (Description) VALUES (\'Regular scheduled class\');
INSERT INTO Lesson_Reason (Description) VALUES (\'Extra practice
session\'); INSERT INTO Lesson_Reason (Description) VALUES (\'Exam
preparation\'); INSERT INTO Lesson_Reason (Description) VALUES (\'Guest
lecture\'); INSERT INTO Lesson_Reason (Description) VALUES
(\'Introduction lecture\');

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Lesson_Replacment
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-- INSERT INTO
Lesson_Replacment (Reason, RescedualDate) VALUES (\'Class not
avaliable\', \'2025-09-30\'), (\'Professor illness\',\'2025-09-22\'),
(\'Technical issues\',\'2024-03-13\'), (\'Other\',\'2020-05-23\');

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Category
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
INSERT INTO Category (Name, Description) VALUES (\'Programming\',
\'Software development courses\'), (\'Design\',\'Graphic and UI/UX
design\'), (\'Business\', \'Business and management\'), (\'Language\',
\'Language learning courses\'), (\'Mathematics\', \'Math and statistics
courses\');

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Course
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
ALTER TABLE Course ALTER COLUMN DependenceID DROP NOT NULL;

INSERT INTO Course (Name, Description, startingDate, EndingDate,
CategoryID, DependenceID) VALUES (\'Python Programming\', \'Introduction
to Python programming language\', \'2024-01-15\', \'2024-03-15\',
(SELECT CategoryID FROM Category WHERE Name=\'Programming\'),NULL);

INSERT INTO Course (Name, Description, startingDate, EndingDate,
CategoryID, DependenceID) VALUES (\'Web Development\', \'Full-stack web
development course\', \'2024-02-01\', \'2024-05-01\', (SELECT CategoryID
FROM Category WHERE Name=\'Programming\'), NULL);

INSERT INTO Course (Name, Description, startingDate, EndingDate,
CategoryID, DependenceID) VALUES (\'Graphic Design Fundamentals\',
\'Basic principles of graphic design\', \'2024-01-20\', \'2024-04-20\',
(SELECT CategoryID FROM Category WHERE Name=\'Design\'), NULL);

INSERT INTO Course (Name, Description, startingDate, EndingDate,
CategoryID, DependenceID) VALUES (\'Business Management\',
\'Introduction to business administration\', \'2024-03-01\',
\'2024-06-01\', (SELECT CategoryID FROM Category WHERE
NAME=\'Business\'), NULL);

INSERT INTO Course (Name, Description, startingDate, EndingDate,
CategoryID, DependenceID) VALUES (\'Data Analysis\', \'Data analysis
with Python and SQL\', \'2024-02-15\', \'2024-05-15\', (SELECT
CategoryID FROM Category WHERE NAME=\'Mathematics\'), NULL);

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Course_Dependenc
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-- INSERT INTO
Course_Dependenc (Description, CourseID) VALUES (\'Requires basic
programming knowledge\', (SELECT CourseID FROM Course WHERE
Name=\'Python Programming\'));

INSERT INTO Course_Dependenc (Description, CourseID) VALUES (\'Requires
basic programming knowledge\', (SELECT CourseID FROM Course WHERE
Name=\'Web Development\'));

INSERT INTO Course_Dependenc (Description, CourseID) VALUES (\'Advanced
course requires completion of beginner course\', (SELECT CourseID FROM
Course WHERE Name=\'Data Analysis\'));

INSERT INTO Course_Dependenc (Description, CourseID) VALUES (\'No
prerequisites required\', (SELECT CourseID FROM Course WHERE
Name=\'Business Management\'));

INSERT INTO Course_Dependenc (Description, CourseID) VALUES (\'Basic
design principles recommended\', (SELECT CourseID FROM Course WHERE
Name=\'Graphic Design Fundamentals\'));

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into UPDATING Course TABLE
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
\-- First Method which it works: UPDATE Course SET DependenceID = 1
WHERE CourseID = 1; UPDATE Course SET DependenceID = 2 WHERE CourseID =
2; UPDATE Course SET DependenceID = 3 WHERE CourseID = 3; UPDATE Course
SET DependenceID = 4 WHERE CourseID = 4; UPDATE Course SET DependenceID
= 5 WHERE CourseID = 5;

ALTER TABLE Course ALTER COLUMN DependenceID SET NOT NULL; \--Second
Methosd it is not giving the reference to the rows \-- UPDATE Course \--
SET DependenceID = ( \-- SELECT DependenceID \-- FROM Course_Dependenc
\-- WHERE Course_Dependenc.CourseID = Course.CourseID \-- ) \-- WHERE
DependenceID IS NULL; \--Third Method, it is not giving the reference to
the rows as well. \-- UPDATE Course \-- SET DependenceID= (SELECT
DependenceID FROM Course_Dependenc WHERE CourseID=(SELECT CourseID FROM
Course WHERE Name=\'Python Programming\')) \-- WHERE Name=\'Python
Programming\';

\-- UPDATE Course \-- SET DependenceID = ( SELECT DependenceID FROM
Course_Dependenc \-- WHERE CourseID = (SELECT CourseID FROM Course WHERE
Name = \'Web Development\') ) \-- WHERE Name = \'Web Development\';

\-- UPDATE Course \-- SET DependenceID = ( SELECT DependenceID FROM
Course_Dependenc \-- WHERE CourseID = (SELECT CourseID FROM Course WHERE
Name = \'Graphic Design Fundamentals\') ) \-- WHERE Name = \'Graphic
Design Fundamentals\';

\-- UPDATE Course \-- SET DependenceID = ( SELECT DependenceID FROM
Course_Dependenc \-- WHERE CourseID = (SELECT CourseID FROM Course WHERE
Name = \'Business Management\')) \-- WHERE Name = \'Business
Management\';

\-- UPDATE Course \-- SET DependenceID = ( SELECT DependenceID FROM
Course_Dependenc \-- WHERE CourseID = (SELECT CourseID FROM Course WHERE
Name = \'Data Analysis\') ) \-- WHERE Name = \'Data Analysis\';

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into CourseTheme
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--

INSERT INTO CourseTheme (Name, Description, CourseID) VALUES (\'Python
Basics\', \'Variables, data types, and basic syntax\', (SELECT CourseID
FROM Course WHERE Name=\'Python Programming\'));

INSERT INTO CourseTheme(Name, Description, CourseID) VALUES (\'Functions
and Modules\', \'Creating and using functions and modules\', (SELECT
CourseID FROM Course WHERE Name=\'Python Programming\'));

INSERT INTO CourseTheme(Name, Description, CourseID) VALUES
(\'HTML/CSS\', \'Front-end web development basics\', (SELECT CourseID
FROM Course WHERE Name=\'Web Development\')), (\'JavaScript\',
\'Client-side programming\', (SELECT CourseID FROM Course WHERE
Name=\'Web Development\')), (\'Color Theory\', \'Understanding color in
design\', (SELECT CourseID FROM Course WHERE Name=\'Graphic Design
Fundamentals\')), (\'Typography\', \'Fonts and text design\', (SELECT
CourseID FROM Course WHERE Name=\'Graphic Design Fundamentals\')),
(\'Business Strategy\', \'Strategic planning and execution\', (SELECT
CourseID FROM Course WHERE Name=\'Business Management\')), (\'Data
Visualization\', \'Creating charts and graphs\', (SELECT CourseID FROM
Course WHERE Name=\'Data Analysis\'));

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Building
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
INSERT INTO Building (Name, Address, Description) VALUES (\'Main
Campus\', \'123 University Ave\', \'Primary academic building\'),
(\'Tech Center\', \'456 Innovation St\', \'Technology and computer
labs\'), (\'Arts Building\', \'789 Creative Lane\', \'Design and arts
department\'), (\'Business Hall\', \'321 Commerce Rd\', \'Business
studies center\');

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Classroom
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
INSERT INTO Classroom (Name, Number, Description, BuildingID) VALUES
(\'Programming Lab\', \'LAB-101\', \'Computer programming laboratory\',
(SELECT BuildingID FROM Building WHERE Name=\'Tech Center\')),
(\'Lecture Hall A\', \'LHA-201\', \'Large lecture hall\', (SELECT
BuildingID FROM Building WHERE Name=\'Main Campus\')), (\'Design
Studio\', \'DS-301\', \'Creative design workspace\', (SELECT BuildingID
FROM Building WHERE Name=\'Main Campus\')), (\'Conference Room\',
\'CR-102\', \'Small group meeting room\', (SELECT BuildingID FROM
Building WHERE Name=\'Arts Building\')), (\'Computer Lab B\',
\'LAB-202\', \'General computer lab\', (SELECT BuildingID FROM Building
WHERE Name=\'Tech Center\'));

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into WorkStation
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-- INSERT
INTO WorkStation (ClassroomID, Name, Number, Address, Description)
VALUES ((SELECT ClassroomID FROM Classroom WHERE Number=\'LAB-101\'),
\'Developer Station 1\', \'WS-101\', \'192.168.1.101\', \'Primary
development workstation\'), ((SELECT ClassroomID FROM Classroom WHERE
Number=\'LAB-202\'), \'Developer Station 2\', \'WS-102\',
\'192.168.1.102\', \'Secondary development workstation\'), ((SELECT
ClassroomID FROM Classroom WHERE Number=\'LHA-201\'), \'Instructor
Station\', \'WS-201\', \'192.168.1.201\', \'Lecturer workstation\'),
((SELECT ClassroomID FROM Classroom WHERE Number=\'DS-301\'), \'Design
Station 1\', \'WS-301\', \'192.168.1.301\', \'Graphic design
workstation\');

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Type_equipment
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-- INSERT INTO
Type_equipment (Name, registerNumber, ShortName) VALUES (\'Desktop
Computer\', \'COMP-001\', \'PC\'), (\'Projector\', \'PROJ-001\',
\'PROJ\'), (\'Projector\', \'PROJ-002\', \'PROJ\'), (\'Whiteboard\',
\'WB-001\', \'WB\'), (\'Printer\', \'PRINT-001\', \'PRINT\'), (\'Network
Switch\', \'NET-001\', \'SWITCH\');

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Equipment
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
INSERT INTO Equipment (ClassroomID,
Name,InventoryNumber,InstallationDate, Description, typeID) VALUES
((SELECT ClassroomID From Classroom WHERE Number=\'LAB-101\'), \'Dell
Workstation\', \'INV-COMP-001\', \'2023-01-15\', \'High-performance
computer\', (SELECT typeID FROM Type_equipment WHERE
registerNumber=\'PROJ-001\' ));

INSERT INTO Equipment (ClassroomID,
Name,InventoryNumber,InstallationDate, Description, typeID) VALUES
((SELECT ClassroomID From Classroom WHERE Number=\'LHA-201\'), \'Epson
Projector\', \'INV-PROJ-001\', \'2023-02-20\', \'HD Projector\', (SELECT
typeID FROM Type_equipment WHERE registerNumber=\'PROJ-002\'));

INSERT INTO Equipment (ClassroomID,
Name,InventoryNumber,InstallationDate, Description, typeID) VALUES
((SELECT ClassroomID From Classroom WHERE Number=\'DS-301\'),
\'Interactive Whiteboard\', \'INV-WB-001\', \'2023-03-10\', \'Smart
whiteboard\', (SELECT typeID FROM Type_equipment WHERE
registerNumber=\'WB-001\')),

((SELECT ClassroomID From Classroom WHERE Number=\'DS-301\'), \'HP Laser
Printer\', \'INV-PRINT-001\', \'2023-01-25\', \'Network printer\',
(SELECT typeID FROM Type_equipment WHERE registerNumber=\'PRINT-001\'));

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Lesson
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
ALTER TABLE lesson ALTER COLUMN ReplacementID DROP NOT NULL; \--I want
to add a condtion like this, when the classroomID is not Null it means
that the lesson is provided and no need for replacement

INSERT INTO lesson (DATE,Name, Status, onlinclassname, LinktoClass,
Descrip_Online,TeacherID, ThemeID, ReasonID, ClassroomID, ReplacementID)
VALUES (\'2025-09-24\',\'Database Fundementals\',\'Face-to-Face\', null,
null, null, (SELECT TeacherID FROM Teacher WHERE LastName=\'Liam\' AND
FirstName=\'Donald\' AND MiddleName=\'Jan\'), (SELECT ThemeID FROM
CourseTheme WHERE Name=\'Data Visualization\'), (SELECT ReasonID FROM
Lesson_Reason WHERE Description=\'Introduction lecture\'), (SELECT
ClassroomID FROM Classroom WHERE Number=\'LAB-101\'), NULL );

INSERT INTO lesson (DATE,Name, Status, onlinclassname, LinktoClass,
Descrip_Online,TeacherID, ThemeID, ReasonID, ClassroomID, ReplacementID)
VALUES (\'2020-04-01\',\'Python Introduction\',\'Face-to-Face\', null,
null, null, (SELECT TeacherID FROM Teacher WHERE LastName=\'Mia\' AND
FirstName=\'Muzamil\' AND MiddleName=\'\'), (SELECT ThemeID FROM
CourseTheme WHERE Name=\'Python Basics\'), (SELECT ReasonID FROM
Lesson_Reason WHERE Description=\'Extra practice session\'), (SELECT
ClassroomID FROM Classroom WHERE Number=\'CR-102\'), NULL );

INSERT INTO lesson (DATE,Name, Status, onlinclassname, LinktoClass,
Descrip_Online,TeacherID, ThemeID, ReasonID, ClassroomID, ReplacementID)
VALUES (\'2024-01-16\', \'HTML Basics\', \'Online\', \'HTML-Basics\',
\'https://meet.google.com/abc-123\', \'Introduction to HTML
programming\', (SELECT TeacherID FROM Teacher WHERE LastName=\'Khan\'
AND FirstName=\'Mahmmod\'), (SELECT ThemeID FROM CourseTheme WHERE
Name=\'HTML/CSS\'), (SELECT ReasonID FROM Lesson_Reason WHERE
Description=\'Regular scheduled class\'), (SELECT ClassroomID FROM
Classroom WHERE Number=\'LAB-202\'), (SELECT ReplacementID FROM
Lesson_Replacment WHERE Reason=\'Technical issues\' )); SELECT\*FROM
Teacher;

INSERT INTO lesson (DATE,Name, Status, onlinclassname, LinktoClass,
Descrip_Online,TeacherID, ThemeID, ReasonID, ClassroomID, ReplacementID)
VALUES (\'2024-01-25\', \'Color Theory Fundamentals\', \'Face-to-Face\',
NULL, NULL, NULL, (SELECT TeacherID FROM Teacher WHERE
LastName=\'Laura\' AND FirstName=\'Josep\' And MiddleName=\'Josee\'),
(SELECT ThemeID FROM CourseTheme WHERE Name=\'Typography\'), (SELECT
ReasonID FROM Lesson_Reason WHERE Description=\'Introduction lecture\'),
(SELECT ClassroomID FROM Classroom WHERE Number=\'DS-301\'), NULL);

SELECT\*FROM lesson;
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Status
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
INSERT INTO Status (Name, Discription) VALUES (\'Active\', \'Currently
active\'), (\'Completed\', \'Successfully finished\'), (\'Dropped\',
\'Left the course\'), (\'On Hold\', \'Temporarily paused\'),
(\'Excellent\', \'Outstanding performance\'), (\'Good\', \'Satisfactory
performance\'), (\'Poor\', \'Needs improvement\'); SELECT\*FROM country;
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Student
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
INSERT INTO Student (FirstName, SecondName, NikeName, Phone, Address,
Email, AdmissionDate, Description, CountryID) VALUES (\'Mike\',
\'Johnson\', \'MikeJ\', \'+1-555-0201\', \'123 Student St, london\',
\'mike.johnson@student.edu\', \'2012-01-10\', \'Computer Science
major\', (SELECT CountryID FROM Country WHERE CodeNumber=\'89\'));

INSERT INTO Student (FirstName, SecondName, NikeName, Phone, Address,
Email, AdmissionDate, Description, CountryID) VALUES (\'Hans\',
\'Schmidt\', \'HansS\', \'+49-555-0203\', \'79 Student Str Berlin\',
\'hans.schmidt@student.edu\', \'2024-01-10\', \'Business student\',
(SELECT CountryID FROM Country WHERE CodeNumber=\'049\'));

INSERT INTO Student (FirstName, SecondName, NikeName, Phone, Address,
Email, AdmissionDate, Description, CountryID) VALUES (\'Khan\',
\'Bacha\', \'KhanBacha\', \'+49-555-0203\', \'39 main Str, Kabul\',
\'Khan.Bacha@gmail.com\', \'2020-03-23\', \'Analytic\', (SELECT
CountryID FROM Country WHERE CodeNumber=\'093\')), (\'Fatima\',
\'Ahmadi\', \'FatimaA\', \'+93-555-0204\', \'321 Student Rd, Paris\',
\'fatima.ahmadi@student.edu\', \'2024-01-10\', \'Programming
enthusiast\', (SELECT CountryID FROM Country WHERE CodeNumber=\'033\')),
(\'David\', \'Brown\', \'DavidB\', \'+1-555-0205\', \'654 Student Lane,
Town\', \'david.brown@student.edu\', \'2024-01-10\', \'Data science
student\', (SELECT CountryID FROM Country WHERE CodeNumber=\'002\'));

SELECT\*FROM Student;
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Student_Course/StudentPerformance
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
Insert into StudentPerformance(Marks, status_id, CourseID, StudentID)
Values (5,(SELECT status_id FROM Status WHERE
Name=\'Excellent\'),(SELECT CourseID FROM Course WHERE Name=\'Web
Development\'), (SELECT StudentID FROM Student WHERE FirstName=\'Khan\'
AND SecondName=\'Bacha\') );

Insert into StudentPerformance(Marks, status_id, CourseID, StudentID)
Values (5,(SELECT status_id FROM Status WHERE Name=\'Active\'),(SELECT
CourseID FROM Course WHERE Name=\'Python Programming\'), (SELECT
StudentID FROM Student WHERE FirstName=\'David\' AND
SecondName=\'Brown\') );

Insert into StudentPerformance(Marks, status_id, CourseID, StudentID)
Values (3,(SELECT status_id FROM Status WHERE Name=\'Poor\'),(SELECT
CourseID FROM Course WHERE Name=\'Business Management\'), (SELECT
StudentID FROM Student WHERE FirstName=\'Hans\' AND
SecondName=\'Schmidt\')), (4,(SELECT status_id FROM Status WHERE
Name=\'Good\'),(SELECT CourseID FROM Course WHERE Name=\'Data
Analysis\'), (SELECT StudentID FROM Student WHERE FirstName=\'Fatima\'
AND SecondName=\'Ahmadi\') );

\-- SELECT\*FROM StudentPerformance;

\-- SELECT\* FROM Course C full join StudentPerformance SC ON
C.CourseID=SC.CourseID \-- FULL JOIN Student S on
SC.StudentID=S.StudentID;

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Student_Plan
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
INSERT INTO Student_Plan (Planned_Start, Planned_Finish,
CourseID,StudentID) VALUES (\'2024-01-15\', \'2024-03-15\', (SELECT
CourseID FROM Course WHERE Name=\'Data Analysis\'), (SELECT StudentID
FROM Student WHERE FirstName=\'Fatima\')), (\'2024-02-01\',
\'2024-05-01\', (SELECT CourseID FROM Course WHERE Name=\'Python
Programming\'), (SELECT StudentID FROM Student WHERE
FirstName=\'Mike\')), (\'2024-01-20\', \'2024-04-20\', (SELECT CourseID
FROM Course WHERE Name=\'Business Management\'), (SELECT StudentID FROM
Student WHERE FirstName=\'David\')), (\'2024-03-01\', \'2024-06-01\',
(SELECT CourseID FROM Course WHERE Name=\'Web Development\'), (SELECT
StudentID FROM Student WHERE FirstName=\'Hans\'));

\--SELECT\*FROM Student_Plan;

\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--Insertion
into Student_Plan
\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\-\--
INSERT INTO Lesson_Attendance (status, Comments, Description, LessonID,
StudentID) VALUES (\'Present\', \'Active participant\', \'Attended full
session\', (SELECT LessonID From Lesson WHERE Name=\'Database
Fundementals\'), (SELECT StudentID FROM Student WHERE
FirstName=\'Fatima\')), (\'Present\', \'Good engagement\',
\'Participated in exercises\', (SELECT LessonID From Lesson WHERE
Name=\'HTML Basics\'), (SELECT StudentID FROM Student WHERE
FirstName=\'Mike\')), (\'Absent\', \'Sick leave\', \'Medical absence\',
(SELECT LessonID From Lesson WHERE Name=\'Color Theory Fundamentals\'),
(SELECT StudentID FROM Student WHERE FirstName=\'Hans\')), (\'Late\',
\'15 minutes late\', \'Traffic delay\', (SELECT LessonID From Lesson
WHERE Name=\'Python Introduction\'), (SELECT StudentID FROM Student
WHERE FirstName=\'David\'));

\--SELECT\*FROM Lesson_Attendance; SELECT\*FROM Student S JOIN
Lesson_Attendance LA ON S.StudentID=LA.StudentID JOIN Lesson L on
L.LessonID=LA.LessonID;
