# MIST4610Disney
This repository consists of my MIST 4610 Disney Database project.

**Team Members**
Mahathi - https://github.com/mrb74060/Disney.git
Morgan - https://github.com/morganlemmings
Clark - https://github.com/clarkfarrell2/Disney
Melissa - https://github.com/melissatran0 

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

1. Query 1 retrieves the movieID and movieTitle from the Movie table for every movie that does not have a corresponding entry in the Merchandise table. It uses a NOT EXISTS subquery to check whether a given movieID appears in the Merchandise table. If no matching row exists, the movie is included in the results.

<img width="844" height="718" alt="image" src="https://github.com/user-attachments/assets/debbb249-c2bd-453c-b595-0944acb4dff2" />

This query allows managers to identify which movies in the catalog have not yet been leveraged for merchandise opportunities. Since merchandise sales can be a significant revenue stream, spotting movies without merchandise helps decision‑makers recognize untapped potential. These results can guide marketing teams and product developers to prioritize which movies might benefit from new merchandise lines, ensuring that popular or overlooked titles are not missing out on additional revenue. By focusing on movies without merchandise, managers can strategically expand offerings and maximize profitability.

2. This query retrieves the location and opening date of each Disney Park from the Park table and orders the results in descending order by the park’s opening date.

<img width="463" height="311" alt="image" src="https://github.com/user-attachments/assets/268d71e6-4f5f-47bb-b7c4-67b141cd566b" />

Understanding the relative age of each park helps Disney management schedule renovations, maintenance, and anniversary events more effectively. For example, older parks may require additional maintenance, while upcoming park anniversaries can be leveraged for special promotions or themed events.

3. This query finds all movies released after 2020 with box office sales higher than the average box office sales, list greatest earnings to least.

<img width="817" height="416" alt="image" src="https://github.com/user-attachments/assets/d366379f-5b78-4552-815b-8d839a17391a" />

Managers want to know so that they can quickly find which movies were most successful and which genres are trending since 2020. By identifying these new trending movies, they can identify what titles might deserve a park attraction or merchandise line so they can maxamize interest with customers, therefore maxamizing profit. By ordering in descending order there can be the most profitable movies with the most potential to the least, out of the movies greater than the average.

4. This query lists all customers whose favorite park is Epcot.

<img width="790" height="748" alt="image" src="https://github.com/user-attachments/assets/c53cb63e-6de1-495d-a21c-418a01087761" />

Marketing wants to target customers based on park preference, so by filtering customers by park preference, they can target their Epcot marketing promotions, such as discounts for Epcot-specific stores or advertising for new Epcot attractions to the right customers.

5. This query finds revenue from merchandise per park.

<img width="837" height="342" alt="image" src="https://github.com/user-attachments/assets/16dce08b-1475-4a9b-a832-594f33d87be1" />

This shows which disney parks bring in the most money from selling merchandise, helps managers see where profits are highest + where to restock faster as well as where new marketing efforts might be needed (for the lower revenues).

This query calculates the total revenue and number of merchandise units sold for each park location, but it only includes purchases made after January 1st, 2023 and merchandise items priced at $25 or higher. It uses multiple table joins to connect purchases, merchandise, stores, and parks, and applies a multi-condition WHERE clause to focus on recent, higher-value sales. This report helps  Disney’s management identify which parks are generating the most revenue from merchandise within the current year. By filtering for recent, higher-priced items, it highlights the most profitable markets and spending trends.

6. This query calculates the total franchise revenue generated by Disney movies based on their release year. It does so by joining the Movie, Merchandise, and Purchase tables to connect movie release dates with merchandise sales. The SUM(Merchandise.price) function computes the total revenue for each release year, and the results are grouped by the movie’s release year and ordered chronologically.

<img width="842" height="738" alt="image" src="https://github.com/user-attachments/assets/a382968a-f48e-4bda-ab6c-3d4b87d456fa" />

This information helps Disney identify which release years continue to generate significant merchandise revenue, profitability trends from over the years. By seeing which years movies still perform well in sales, management can make strategic decisions about which franchises deserve renewed marketing, new merchandise lines, or future sequels. This query ultimately helps maximize profit through data insight into franchise longevity as well as finding profitable merchandise to maximize.

7. Query 7 identifies customers who have not made any purchases since January 1, 2008. It joins the Customer table with the Purchase table on the customer ID. The WHERE NOT EXISTS subquery checks whether a given customer has any purchase records dated on or after January 1, 2008. If no such record exists, that customer is included in the results.

<img width="683" height="589" alt="image" src="https://github.com/user-attachments/assets/3c53f40e-dcd2-47df-84c7-8e181ae17b88" />

Query 7 allows managers to identify customers who have been inactive for a long period of time (no purchases since 2008). These customers represent a segment that may require re‑engagement strategies, such as targeted marketing campaigns, loyalty incentives, or personalized outreach to encourage them to return. By listing their names and email addresses, managers can directly contact these customers with tailored offers. This insight helps the business: reconnect with lapsed customers, understand long‑term churn patterns, and design campaigns to win back inactive segments. Ultimately, this query supports customer relationship management by highlighting opportunities to revive dormant customer accounts and increase revenue through reactivation.

8. Query 8 retrieves customer information alongside details about family rides at their favorite park. It joins four tables: Customer, Visit, Park, and Attraction. The query calculates each customer’s visit duration and filters results to only include customers whose visit duration is longer than the average visit duration across all visits. It further restricts results to customers whose favorite park is either Magic Kingdom or Hollywood Studios, and only lists attractions of type Family Ride at those parks. Results are ordered by visit duration in descending order, so the longest visits appear first.

<img width="813" height="466" alt="image" src="https://github.com/user-attachments/assets/cd5f87d3-6ed0-498e-8a50-3d742ba6aa2e" />

Query 8 helps managers identify customers who spend more time than average at Disney parks, specifically those who favor Magic Kingdom or Hollywood Studios. By also listing the family rides available at their favorite park, managers can see which attractions are most relevant to these high‑engagement customers. This information is valuable because knowing their favorite parks and the family rides available there helps managers design targeted promotions, and personalized experiences and insights can guide resource allocation (e.g., staffing, ride maintenance, or marketing) toward attractions that appeal to long‑stay visitors. Ordering by visit duration makes it easy to prioritize the most loyal and engaged customers for outreach or rewards programs.

9. Query 9 calculates each genre’s average, highest, and lowest, and count of movies (total) while focusing on recent, relevant genres (action, adventure, fantasy) released after 2010. It then uses a subquery to keep only the genres whose average box office exceeds the overall average across all movies.

<img width="842" height="366" alt="image" src="https://github.com/user-attachments/assets/6ec7061c-9d07-4db6-b509-2f01a2cb44ea" />

This query calculates each genre’s average, highest, and lowest, and count of movies (total) while focusing on recent, relevant genres (action, adventure, fantasy) released after 2010. It then uses a subquery to keep only the genres whose average box office exceeds the overall average across all movies. Disney can identify which genres consistently outperform the company’s average at the box office. They can also focus on budgets, marketing, and future projects on profitable genres. This query will also allow them to detect whether newer releases maintain the same financial success as past films. 

10. Query 10 joins the Movie, Casting, and Actor tables to link actors with the films they have appeared in. It groups results by each actor’s details and calculates two aggregates: the total number of movies and the highest box office revenue among those movies. The HAVING clause filters the results to only include actors who have appeared in at least three movies and who have starred in at least one film with box office earnings above the overall average across all movies. The final output lists each qualifying actor along with their personal details, movie count, and best box office performance.

<img width="893" height="436" alt="image" src="https://github.com/user-attachments/assets/b269d4d1-2aea-4f05-ac5b-af886eb72b60" />

To Find the highest frequency in terms of the actor who appears in the most movies, so that Disney can identify some of the most popular actors. Then, they can have a special featured event at the Disney park with one or more of the most popular actors so that they can gain publicity and more customers. Finding only actors who have been in a movie with a box office in the greater 50% of all box offices will ensure that they have truly been in a popular movie.

**Database Information:**
Name of Database: ns_Group4
