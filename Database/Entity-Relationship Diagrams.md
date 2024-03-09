

Answer to the demo exercises: 

* Explain the terms super key, candidate key and primary key for entities and relationships


	Super key: A set of attributes that uniquely identifies any entities from among all possible entities in the entity class that may appear in the database.

	Candidate key: Is a minimal super key, meaning it's a subset of a super key and cannot be further reduced.

	Primary key: The primary key is a specific chosen candidate key for a relation,it serves as the main unique identifier for tuples within that relation. It enforces entity integrity and establish relationships between the tables. 																																																															![[Screenshot from 2024-03-07 14-26-46 1.png]]

* a) The course_dept serves as a relationship set between the tables Course and department.  it has many to one cardinality, which is shown by arrows.  In particular, a course can only have a single department, while a department can have many courses. cardinality

* b) Takes serves as a relationship set between Section and student with dashed lines linking to the participating entity, grade. 

* c) Because it contains three different identifiers.