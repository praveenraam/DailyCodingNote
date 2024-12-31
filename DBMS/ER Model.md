Topic No : 5
Previous Topic : [[Data Models]]
Next Topic : [[RDBMS]]
ER Diagram Drawing Guide : [[Symbols in ER]]

### Terminologies

##### Entities :
- A "thing" in the world with an existence
- It can be a an object with physical existence (Tangible Entity)  Ex : human, house or with a conceptual existence (Intangible Entity) Ex : Course, job.

##### Types of Entity 
- Strong Entity : Entity with primary key Attributes.
- Weak Entity : Entity doesn't have primary key Attributes.

##### Entity Set
A collection of entities with same attributes

##### Attributes :
These are the properties of the Entity.
Ex : If person is a Entity then his name, age, address are Attributes.

Attributes are of many types.
- **Composite Attributes** : Attributes that are divided more, Ex : name into first, middle and last name.
- **Simple Attributes** : Attributes that can't be divided, Ex : Age.
- **Single Value Attributes** : The attribute can have only one single value for the Entity.
- **Multivalued Attributes** : The attribute can have more than only value, Ex : College Degrees
- **Derived Attributes** : The attribute that can be found from another, Ex : Age from DOB
- **Stored Attributes** : The attribute from which the other Attribute are derived, Ex : DOB
- **Complex Attributes** : The Attributes with the combination both composite and multivalued.
	Ex : {College Degree(College, year, Degree, Field)}, composite values will be within { }, and multivalued within ( ).
- **Key Attributes** : When the data in row is completely unique without duplicated. Ex : Roll_number. These won't allow null value.

##### 'null' value :
'null' value represent unknown or doesn't exist. 

### What is a relation in ER Models :
A relation is the connection between the two entities, representing how various objects or concepts related to each other in system.

### Types of Relationship Sets :

##### Unary Relation : 
When there is only one ENTITY set is participation in the relation, then it is called unary relation.
Ex : 
![[Pasted image 20241231100240.png]]

##### Binary Relation : 
When there are two different ENTITY set are participating in the relation, then it called Binary relation.
Ex : 
![[Pasted image 20241231100413.png]]
##### Ternary Relation :
When there are three ENTITY set are participating in relation, then it is called Ternary relation.
![[Pasted image 20241231100510.png]]

##### N-nary Relation : 
When there are n entities set participating in a relationship, the relationship is called an N-ary relationship.

### What is cardinality :
The number of time the ENTITY is participating in the relationship.
##### One to One : 
When each entity in each entity set can take part only once in the relationship, the cardinality is one-to-one.
Ex : One person can be married to another one person
##### One to Many : 
In one to many relation where each entity can be related to more than one entity
Ex : One student can register multiple courses
##### Many to One :
When entities in one entity set can take part only once in the relationship set and entities in other entity sets can take part more than once in the relationship.
Ex : multiple students can register a single course
##### Many to Many :
When entities in all entity sets can take part more than once in the relationship.
Ex : Employees working on multiple projects

### Participating Constrains
##### Total Participation :
The total participation is nothing but Entity set must participate in a relationship.
Ex : Each student must enroll a course

##### Partial Participation :
This Entity Set may or may not participate in the relationship
Ex : some courses may not be choose by student.