
### Entity relationship diagrams
Entities - squares
Attributes - ovals
Keys - underlined attributes

#### Entity Sets
Keys must be unique. They can be formed from some algorithm. The safe thing to use as a key is a synthetic key that is automatically generated and only has meaning in the database.

##### Relationships
Relationships (diamonds) represent verbs of our domain. Relationships are between entities

Many to many relationships - for X <-> Y, any S can be related to zero or more Ys, and any Y can be related to zero or more Xs.

Relationships can also have attributes, e.g. between Movie and Person, the Acted_In relationship can have attribute Role

A multi-valued attribute can be used to store a comma separated list of an attribute. In a real database, this violates 1NF.

Ternary relationships can be used to get around this. Acted_In can have another entity connected to it - Role, which can then store multiple roles.

Consider scope when modelling something as an attribute or entity.

Many to one relationships - e.g. each employee works in one department, but one department has many employees.

Weak entities are entities that depend on the existence of another entity. The key of a weak entity is called a discriminator. Here, to uniquely identify an AlternativeTitle you need the alt id and movie id.
![[WeakEntity.png]]

Sub entities can inherit the attributes (including keys) and relationships of the parent entity.
![[Pasted image 20251021114808.png]]