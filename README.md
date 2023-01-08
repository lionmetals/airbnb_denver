Welcome to the airbnb_denver wiki!

<h1>Which Airbnb hosts would most likely need a cleaning service?</h1>
<img width="250" alt="Screenshot 2023-01-04 at 2 10 05 PM" src="https://user-images.githubusercontent.com/114360846/210884901-3c99a898-c186-4c2f-a1ce-9c17d372e380.png">

<h2>Scenario</h2>
My friend has a cleaning business in Denver, CO. He is trying to generate leads for Airbnb hosts who would be the most likely to want to hire his cleaning service. To do this, I ran two separate queries to determine which Airbnb hosts have the:
<ol>
<li><b>Lowest cleanliness scores</b></li>
<li><b>Highest amount of the word "dirty" in their reviews</b></li>
</ol> 

<h2> Programming Tool Used:</h2>
<b>SQL via BigQuery</b>: Great tool for analyzing large data-sets 

<h2>Prepare</h2>
<b>Data:</b> http://insideairbnb.com/get-the-data
<br>
<b>Loading Data:</b> Loaded listings.csv and reviews.csv into Bigquery

<h2>Lowest Cleanliness Score</h2>
My friend wanted room_type to be "Entire home/apt" and to rank the list by cleanliness score (descending). I noticed there were many cleanliness scores that were null, so made a query where the review_scores_cleanliness was not null.
<img width="900" alt="Screenshot 2023-01-04 at 2 10 05 PM" src="https://user-images.githubusercontent.com/114360846/210876400-0fe4de76-4f70-4c76-8962-b0467eaa6dbf.png">
<br>
Problem was that there are a lot of listings that aren't active anymore, so made new query where the has_availability column was true:
<img width="900" alt="Screenshot 2023-01-04 at 2 10 05 PM" src="https://user-images.githubusercontent.com/114360846/210877525-ed7d7d94-830b-44f2-b93b-0b3203eb5d46.png">
<br>
This still gave me a large amount of unavailable listings! So, I decided to add another column, number_of_reviews, and set it to be greater than 5. This fixed the issue!
<img width="1000" alt="Screenshot 2023-01-04 at 2 10 05 PM" src="https://user-images.githubusercontent.com/114360846/210877702-1b75e473-54a4-4ff3-a849-30d68a4f4f23.png">
<br>
Below is a screenshot of the .csv file I sent over to my friend detailing the 100 lowest cleanliness score Airbnb's (removed host_names column for anonymity).
<img width="1208" alt="Screenshot 2023-01-05 at 12 54 52 PM" src="https://user-images.githubusercontent.com/114360846/210878301-0fdf484d-80cb-4fc8-acf1-c0c0d51b95fa.png">
<br>

<h2>Highest "dirty" Word Count in Reviews</h2>
I wanted to provide my friend with one more source of data so I decided to find the hosts with the highest count of the word "dirty" in their reviews.
<img width="1000" alt="Screenshot 2023-01-05 at 12 54 15 PM" src="https://user-images.githubusercontent.com/114360846/210880166-34e23dfa-5578-456e-b22f-a893e342a06e.png">
<br>
Screenshot of the .csv file I sent over to my friend detailing the 100 highest amount of "dirty" reviews (again removed host_names column for anonymity).
<img width="910" alt="Screenshot 2023-01-05 at 12 54 15 PM" src="https://user-images.githubusercontent.com/114360846/210878298-6fa173bc-6587-4120-91e0-9720c4a74b5f.png">

<h2>Conclusion</h2>
My friend used the lists I generated to find <i><b>twelve</b></i> new clients during the <i>first day he used the list</i>. He found this list "super helpful" and "a really efficient way to source new clients."
