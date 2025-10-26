# MIST4610Disney
This repository consists of my MIST 4610 Disney Database project.

**Team Members**
Mahathi - https://github.com/mrb74060/Disney.git

**Problem Description:**

The task at hand is to model and build a relational database for the general workings of Disney. The central entities to our data model is the park entity, which represents the physical location of Disney World, and the movie entity. The park entity is relational to the employees who manage the park, the various attractions present at the park, employees who operate the park, disney themed stores at the park, and maps out the relationship to customers who visit the park. The movie entity consists of characters, actors, movie themed merchandise, and casting process. We are interested in accurately modeling these relationships and generating sample data, so that we can operate the disney park efficiently and effectively. The movie aspect of disney is also mapped out to help maximize profit, help with franchise growth, and most importantly help with cross-division coordination. We established a link between the movie and park entities to demonstrate the influence movies have on physical elements in disney stores.

**Explanation of the Data model:**

Our model is based on the Disney Corporation’s key revenue streams, which have represented Disney since its beginning: its famous movies and Disney World. 

The first entity we created was the movie entity, which contains general information about the movie, such as its release date, genre, etc. Inside each movie, many characters can be a part of many movies in the form of sequels. To show this many-to-many relationship, we created an associative entity “Appearance” to show which fabled Disney characters appeared in which movies. 

Characters are voiced by people, so an Actor entity was created with a one-to-many non-identifying relationship with “Character” to show who voices what characters. The modality for the Actor in this relationship is 1 because we are only including characters who have speaking parts and not just every character seen in the movie. Many Disney movies have real people in them, so we created a “Casting” associative entity to relate “Movies” with “Actors” to record what actors are present in different movies. 

Disney makes a lot of revenue from the different merchandise it sells at Disney World, and this merchandise largely contains attributes that come from Disney movies. The merchandise does not have to include these attributes, so we made a non-identifying one-to-many relationship between “Merchandise” and “Movie.” Disney sells their merchandise at different stores across Disney World, so a one-to-many non-identifying relationship was constructed between store and Merchandise. Disney wants to track the facts such as quantity in stock, unit cost, and selling price of each item, so an Inventory table was created; however, inventory is different at each store, so “Store” must become a foreign key through a one-to-many relationship with “Inventory.”

There are different parks at Disney World, such as Epcot, Animal Kingdom, Magic Kingdom, etc., that we want to have information about, such as location and opening date, resulting in the “Park” entity being created. Each park also has different stores and attractions, so one-to-many relationships were created between “Park” and “Store” and “Park” and “Attraction.” Attraction holds information about its name and type, as well as what area of the park it is in. 

Parks are staffed by employees, and we are assuming Disney keeps its employees working in the same park since Disney heavily values consistency and effectiveness. So, “Park” has a one-to-many relationship with “Employee.” “Employee” also holds general information such as title, name, and tenure. 

People who come to Disney World are tracked through the “Customers” entity. Many customers purchase many different merchandise while at Disney World, resulting in an associative entity to track this called “Purchase.” Customers’ visits and other information about the visit are tracked through the “Visit” entity and a one to many relationship is modelled between “Customer” and “Visit.” Lastly, since Disney values its Customers, they like to know which park each customer likes the most so a one to many relationship is mapped between “Customer” and “Park.”

**Data Dictionary:**

<img width="904" height="439" alt="image" src="https://github.com/user-attachments/assets/4900d6ba-0040-4175-9fc9-0070828789a8" />

<img width="947" height="556" alt="image" src="https://github.com/user-attachments/assets/0e5c742a-34bb-4ff0-a498-e931e095fe6a" />

<img width="950" height="366" alt="image" src="https://github.com/user-attachments/assets/abee5818-cf15-4def-81f2-225733a38d57" />

<img width="988" height="493" alt="image" src="https://github.com/user-attachments/assets/902a4cbd-997b-4c1f-ab68-46eef9a8f157" />

<img width="1014" height="612" alt="image" src="https://github.com/user-attachments/assets/41073702-a710-4cec-86a5-41d836904355" />

<img width="1003" height="653" alt="image" src="https://github.com/user-attachments/assets/72c12c8b-7b81-4a9e-9c3a-0399bdf504d6" />

<img width="961" height="448" alt="image" src="https://github.com/user-attachments/assets/981db225-174d-45a4-a493-7f7f75837e3e" />

<img width="952" height="623" alt="image" src="https://github.com/user-attachments/assets/0b3f0d5f-246d-416f-b7f3-c4c789d8cf63" />

<img width="929" height="254" alt="image" src="https://github.com/user-attachments/assets/9eb8ef74-23ff-43a4-937f-5b5d33930932" />

<img width="967" height="304" alt="image" src="https://github.com/user-attachments/assets/5cb01678-6b54-4ddc-bd45-d26bcb9c48d8" />

<img width="938" height="303" alt="image" src="https://github.com/user-attachments/assets/cda53e7b-66c9-4495-90c6-483554d555a6" />

<img width="973" height="431" alt="image" src="https://github.com/user-attachments/assets/27cf14ca-1323-49dd-a644-459c94c54697" />

<img width="970" height="600" alt="image" src="https://github.com/user-attachments/assets/b563e569-901a-4290-82a6-a65865cd8e7a" />

<img width="984" height="485" alt="image" src="https://github.com/user-attachments/assets/97fd29bd-9ff0-4287-bc55-17d8059ea1de" />

**Queries:**

<img width="1050" height="384" alt="image" src="https://github.com/user-attachments/assets/12a92203-034d-42ad-aae9-dccbafd09554" />

















