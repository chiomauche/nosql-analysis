  # UK-food-hygiene-ratings

The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. I was contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

# Part 1: Database and Jupyter Notebook Set Up

* I imported the data provided in the establishments.json file from my Terminal. Named the database uk_food and the collection establishments. Copied the text I used to import my data from my Terminal to a markdown cell in my notebook.
* Within my notebook, I imported the libraries I needed: PyMongo and Pretty Print (pprint).
* I created an instance of the Mongo Client.
* I confirmed that I created the database and loaded the data properly by:
* Listing the databases I have in MongoDB. I confirmed that uk_food was listed.

![Alt text](<Screenshot 2023-10-24 045016.png>)

* I listed the collection(s) in the database to ensure that establishments was there.
* I Found  and displayed one document in the establishments collection using find_one and displayed with pprint.
* I assigned the establishments collection to a variable to prepare the collection for use.


# Part 2: Update the Database

The magazine editors have some requested modifications for the database before I can perform any queries or analysis for them. I made the following changes to the establishments collection:

* I added the following information to the database:
* Found the BusinessTypeID for "Restaurant/Cafe/Canteen" and returned only the BusinessTypeID and BusinessType fields.
* Updated the new restaurant with the BusinessTypeID I found.
* The magazine is not interested in any establishments in Dover, so I checked how many documents contained the Dover Local Authority. Then, removed any establishments within the Dover Local Authority from the database, and checked the number of documents to ensure they were deleted.
* As some of the number values were stored as strings, when they should be stored as numbers, I used update_many to convert latitude and longitude to decimal numbers.Used update_many to convert RatingValue to integer numbers.

# Part 3: Exploratory Analysis

Eat Safe, Love had specific questions they wanted me to answer, which would help them find the locations they wish to visit and avoid.
* I used NoSQL_analysis_starter.ipynb for this section
* I used count_documents to display the number of documents contained in the result.

![Alt text](<Screenshot 2023-10-24 050509.png>)

* I displayed the first document in the results using pprint.
I converted the result to a Pandas DataFrame, printed the number of rows in the DataFrame, and displayed the first 10 rows.

# Questions looked for:
* Which establishments had a hygiene score equal to 20?  
* Which establishments in London had a RatingValue greater than or equal to 4?
* What were the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
* How many establishments in each Local Authority area had a hygiene score of 0? Sorted the results from highest to lowest, and printed out the top ten local authority areas.

     

  