# HBnB Part 1
Part 1 of HBnB and you found diagrams here
---
```
Diagram 1 for Hight-Level Package
```
---
```mermaid
classDiagram
class PresentationLayer {
    <<Interface>>
    +Service
    +API
}
class BusinessLogicLayer {
    +Model
    +Classes
}
class PersistenceLayer {
    +Database
    +Access
}
PresentationLayer --> BusinessLogicLayer : Facade Pattern
BusinessLogicLayer --> PersistenceLayer : Database Operations
```
----
----
```
Diagram 2 Detailed Class Diagram for Business Logic
```
---
```mermaid
classDiagram
class USER {
    - user_id: UUID4
    - first_name: String
	- last_name: String
	- email: String
	- password: String
	- created_at: DateTime
	- updated_at: DateTime
	+ create_account()
	+ login()
	+ update_profile()
	+ delete_account()
}
class Place {
	+ place_id: UUID4
	+ name: String
	+ description: String
	+ location: String
	+ owner_id: UUID4
	+ amenities: List<Amenity>
	+ created_at: DateTime
	+ updated_at: DateTime
	+ add_place()         
	+ update_place()      
	+ delete_place()      
	+ get_place_details() 
}
class Review {
    - review_id: UUID4
    - place_id: UUID4 
	- user_id: UUID4 
	- rating: Integer
	- comment: String 
	- created_at: DateTime
	- updated_at: DateTime
	+ add_review()
	+ update_review()
	+ delete_review() 
	+ get_reviews_for_place()
}
class Amenity {
	- amenity_id: UUID4
	- name: String
	- description: String
	- created_at: DateTime
	- updated_at: DateTime
	+ add_amenity() 
	+ update_amenity()
	+ delete_amenity()
	
}
USER --> Place : 1*
Place --> Review : 1*
Review --> Amenity : 1*
```
---------------------------------------------------------------

---------------------------------------------------------------
```
Diagram 3 Sequence Diagrams for API Calls
```
---
```mermaid

sequenceDiagram
    participant Client
    participant API
    participant User Model
    participant Place Model
    participant Database

    Client ->> API: POST REQUEST
    API ->> User Model: CHECK USER
	API ->> Place Model: VALIDATE DATA
	Place Model ->> Database: SAVE DATA
	Database ->> Place Model: SAVING CONFIRMATION
    Place Model ->> API: SEND NEW PLACE
	API ->> Client: CREATED

