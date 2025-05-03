##### Exercise 7

- Need to store student details SNO, SName, Age, SNO are unique. 
- Needed to store module details MNO, MName, Duration. MNO are unique.
- One student can select many modules, if a module not selected by any student that module will be removed from the syllabus. 

![[Drawing 2025-01-09 13.54.59.excalidraw]]


### Composite attribute

![[Drawing 2025-01-09 14.30.16.excalidraw]]


### Multi value attribute

![[Drawing 2025-01-09 14.33.04.excalidraw]]

#### Design a student database

A database needs to be developed that keeps track of supervision of PhD students. The data requirements are as follows. 
- For each student store the name, student ID and address. Student ID's are unique. As the address consists of stress town and postcode.
- for each lecturer store the name, staff ID and officer number staff ID are unique
- each student has exactly one supervisor. A staff member may supervise a number of students.
- the date when suspension began also need to be store.
- for each research topic store the title and a short description title are unique. 
- each student can be supervised in only one research topic.

![[Drawing 2025-01-09 14.50.35.excalidraw]]


#### Design music database

A database need to be developed that keep track of compact disks , and music pieces recorded on them. together with authors and performers of the prices. The data requirements as the follow: 

- for each disk. We want to store the disk ID, the title and the year of production. Disk ID are unique.
- A pieces of music is recorded on some disk. It has title and a number that indicate on witch track is recorded on the disk. For each disk, a piece is uniquely identified by is track number. 
- for each person that may occur as a author or a performer we want to store the person ID, the name and the nationality. Person ID's are unique. 
- Watch pioneer of music has at least one author who is a person. There are definitely type of authorship. Egg: composer, text writer, or arranger. For each author of a piece. We want to store the type of authorship. 
- each piece of music has at least one former who is a person they are different instruments for a performer. Eg: voice, piano, violin. We want to store for each performer that instrument they have platter during the recording.
![[Drawing 2025-01-10 10.15.47.excalidraw]]

#### video rentals scenario 

The following data model is designed to hold information relating to a video rental store. For this scenario we need to define the following facts

These facts define the requirements which the database must meet and should be agreed between the database users and the database designer prior to physical creation.

The draft effects have been defined as:

The Entry requirement should include: 
- members 
- rentals
- video copies
- video titles
- video categories
- video certification

The entities are related as follows 
- a member can rental one or many video copies 
- a video title may have one or many video copies
- a video copy me rental by zero one or many members 
- a video title can have only one certification associate with it

#add 

# Relational Schema

Concept regular entity into relational schema
#add

#### Convert ***1:1 Relation*** into Relational schema
![[Drawing 2025-01-17 14.31.10.excalidraw]]

#### Convert ***1:M Relation*** into Relational schema
![[Drawing 2025-01-17 15.35.22.excalidraw]]

#### Convert ***M:M Relation*** into Relational schema
![[Drawing 2025-01-17 14.08.31.excalidraw]]

#### Convert ***ISA Relation*** into Relational schema
![[Drawing 2025-01-20 09.32.20.excalidraw]]

#### Convert ***Multivalued Attribute*** initial Relational schema 
![[Drawing 2025-01-20 09.48.49.excalidraw]]


#### Convert ***Composite Attribute*** initial Relational schema
![[Drawing 2025-01-20 10.03.53.excalidraw]]


#### Convert ***Weak Entity*** initial Relational schema
![[Drawing 2025-01-20 10.14.15.excalidraw]]


## ER to Relational Schema - Mapping Algorithm 

Step 1: Mapping of Regular Entities.
Step 2: Mapping of Weak Entities.
Step 3: Mapping of 1:1 Relationships.
Step 4: Mapping of 1:M Relationships.
Step 5: Mapping of M:M / M:N Relationship.
Step 6: Mapping of Multivalued and Composite attributes.
Step 7: Mapping of N - array Relationships.
Step 8: Mapping of ISA Relationships.

Ex:
![[IMG20250120120611.jpg]]

![[Drawing 2025-01-31 09.43.12.excalidraw]]

![[Drawing 2025-01-31 09.54.11.excalidraw]]



## Normal Forms

1st Normal from
- attribute should not be Multivalued or Composite. 
- attribute should be simple and individual. 

2nd Normal from
- Attributes can't depend partially.

3rd Normal from
- Non-prime attributes can't depend on Non-prime attribute.

4th Normal from / Boyce code Normal from
- Prime attribute can't depend on Non-prime attribute.

# Ms sql

![[Drawing 2025-01-31 11.37.23.excalidraw]]


Add basic db quarry 

## Foreign key