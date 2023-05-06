
We made food based personalised recommendation system.

we completed this project in three steps

--- 

First we made a simple content based recommendations for which we started by scrapping data from swiggy to extract the information about food items and restaurants 
Then we calculated tf-idf for each food items description.

And when a user makes a request to find similar food items for a given item cosine similarity is used to find the top 50 similar food items.

Then extra weight is given based on price range and rating and top 10 are suggested to the user.

problem - There is no personalisation.

---

so to add personalisation we decided to add a user profile which will contain preferred cuisine , preferred taste , region , state and using this we made a feature vector for user.
- Indian food items dataset from kaggle.

then matching is done for each food item using cosine similarity and top 50 is extracted and then weight is given on the basis of price and rating and top 10 are shown to the users

Problem - static 
ones the profile is fixed and user change its preference it will not be able to consider that fact

so to make it dynamic

---

we 
