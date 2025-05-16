***Genre Prediction using ML:***
The original source for data was the final_project.ipynb file provided from Ram Kishnore’s previous project. It was modified to collect data from a wider time period.
**How to run?**
Open the GenrePredictionML.ipynb file and run the program cell by cell.
**What does it do?**
Cell 1: Read the dataset and preprocess the data:
Convert the genre column from string to list of strings.
Filter data to rows with release_data between 1990 to 2010
Cell 2: Creates a new dataset with columns title, box_office and genre and sorts them based on box_office
Cell 3: Created a new dataset called genre data and added a column with the number of movies for each genre.
Cell 4: Created a new column to get the average box office for each genre
Cell 5: Plots Genres vs Box office
Cell 6: Plots pie chart with the percentage of movies for each genre
Cell 7: Creates a new data frame called movie_df for genre prediction using plot
Cell 8 - 21:  
Removing Duplicate Values
Adding a label column, i.e. giving numbers to all the genres
Cleaning the plot column using nltk library
Cell 22 - 26:
Training the model and using the Naive Bayes Classifier from the sklearn library to predict genres by using the plot data as features
Cell 27: Showing the confusion matrix as a heat map
Cell 28: Printing the accuracy
**What are the Challenges or Limitations?**
Could use more Data
Better Preprocessing. Eg:
Selecting specific words related to genre
Implemented Neural Networks to learn better
Could use other features to predict



***SpaCy Processing***
**How to run?**
Open the FinalSpaCy.ipynb file and run the program cell by cell.
**What does it do?**
Cell 1: Import spaCy, Counter, pprint, and pandas
Cell 2: load spaCy as “nlp”
Cell 3: Creates a movie_reader function, which loads data from the csv file, and sorts out the movies and the plots that will be analyzed. 
Short films and tv movies are discarded.  
Cell 4: Creates the movie_data (directly from csv) and “movies” dictionary (data for analysis). 
Movies is a dictionary where the titles are keys and the plots are values
Cell 5: Token getter function. Uses nlp to separate out the important words from the plots of the movies
Cell 6: Calls token_getter to get the plots’ tokens
Cell 7: creates a genre_words dictionary, containing movie genres and words associated with each genre.
Cell 8: applies NLP to the genre words dictionary values to allow them to be matched against the plot tokens
Cell 9: defines genre_picker function, which creates for each movie a dictionary of the genres that it contains words relating too
Cell 10: called genre_picker
Cell 11: Defines genre_finder function. This function determines the percentage of words for each movie that apply to a specific genre, 
with the assumption that a genre with a higher percentage means the movie belongs to that genre
Cell 12: Called genre_finder
Cell 13: Defines the “Final Function” which creates a dictionary that contains the title, genres, release date, and box office gross of a movie.
Cell 14: Calls final_function
Cell 15: Saves the results of cell 15 to a csv file
**Challenges:**
long run time made testing difficult
Accuracy could be difficult to determine but was overall considered reliable

***RECOMMENDATION SYSTEM:***
How to run:
Run the recommendation_system.ipynb file after changing the dataset path location(if path of the dataset differs)
Cell1: Import the necessary modules(pandas and sklearn) and define the path
Cell2: Do the preprocessing.Fill the missing values in overview with empty string
Cell3: Initialize a Tfidfvectorizer and define stop words as English to remove the common english words.Use this vectorizer to transform the overview column
Cell4:Calculate the cosine similarity with inbuilt function
Cell 5,6: Convert the title to lower for easier interpretation.Create an alternate output if the given user movie name is not in the dataset. 
Find the index of the title given by the user. Get the cosscore for the given title index. Sort the cosine similarity for the given title.
Get the title name for the first five cosine similarities to get the movie name. Print the Output
Cell 7:Define a weighted mean function or do some other function based on your requirement. 
We converted vote count and vote average to numeric (i got some errors without doing this there was some type error) 
Now create a function to calculate mean rating function for our values. Again do the same function and same steps like the previous recommendation function. 
Just create a new feature for calculation over here we did a product of mean rating and cosine similarity.
Challenges:
While doing the tfidf matrix,we tried to give my defined matrix but for some reason we couldn't get it so we used the sklearn feature.
We tried jaccard instead of cosine similarity first ,we couldn't get a proper output.

Limitations:
Though it's giving recommendations for the given movies there were some unrelated movies in the output. 
For instance if we give spiderman there are few values like arachnophobia,the taking of pelham one two three.This is because it might have same kinda similar overview
Improvements:
Could try a new method to calculate similarity score.We didn't explore other options like jaccard, pearson. We can try those too.
Also for weighted mean am using mean instead of that we could try some other optimal metrics.
The last limitation can be improved by doing a different approach too.

**Actors and Directors with Network:**
How to run:
Run the actors_directors_network.ipynb file after changing the dataset path location(if path of the dataset differs)

Cell1: Import the necessary modules.Preprocess for starring and director by stripping [] and replacing ‘ , ‘ with empty string and split the values with ‘,’. 
Create a new value for dataframe for calculating profit which is the difference between budget and box office. 
Create a new column called year from releasedate using datetime.
Here we defined a function for decade calculation which is year divided(integer division) by 10 and then multiplied to 10.
Drop the nan values where decade has empty values. Give the same weighted mean function.
In the data starring and director may have many values for each movie.So we duplicated the rows for individual actors and directors.
Cell2: Now using groupby function (decade,starring) and agg function ,get weighted rating and profit for both director and actors.
Cell3: Sort the previous thing by decade and then by weighted rating and profit for all the required values. Print the values

Cell 4:Now get the top 10 rated,profitable actors and directors by using sort like we did in the previous values but restrict the head for 10 values.
Create graph for network creating.
Add nodes for actors and directors.Create edge when the actor and director had done the same movie.
Define the parameter and give the layout configuration for the network.
Give legend values.Using pyplot plot our network and give title.
Since we are creating network graph for all decades we are looping it from decade in the dataframe and we are getting the values for top10 actors and directors 
for each decade by masking the dataframe. Finally we passed our values to create a network.
Limitations and Improvements:
We used average rating at first but it would be a biased rating because no of voters varied for every movies,so we opted this weighted approach
Instead of calculating rating based on their performance ,it is calculated based on the movie rating.
We could improve this by including some other metrics to calculate the rating of actor and director.
Same for profitability,it also depends on the movie  instead of the profit brought by the director or actor.This could also be improved by using some other metrics.

**Top Movies:**
How to run:
Run the top_movies.ipynb file after changing the dataset path location(if path of the dataset differs)

Cell1:Import pandas and read the file
Cell2:Create a new column for the year from the release date just getting the year value and drop the values for decade is nan.
Cell3:give the weighted mean function calculation
Cell4:Now get the output values for grossing and rated movies by sorting by decade first and then by box office and weighted rating for both the values.
Use groupby to filter only for the required decade.
Cell5:Since we are passing all decades, iterate in the decade column and pass it to the cell4 function and get the required values for each decade.
Improvements:For rating,we could try a different approach.

**Genre Popularity chart:**
How to run:
Just run genrepopularity.ipynb after changing the dataset path location(if path of the dataset differs)
Cell1:Import the necessary module.Read the file and do the same preprocessing like removing unnecessary values other than alphanumeric characters.
Since the dataset is having so many genre values for a single values.We gotta replicate the rows for each genre in the movie for analytic purpose
Cell2:Then group the dataset by using groupby years and genres  and count the number of genres in each year .
we have used size function and named it as count.Then we calculated the total count of every genres for all the years.
Sort the values for no of movies in genres .At the end  we took the top 10 genres and make it as a list.
Cell3:Now we made a function to calculate genre count for top genres for each year.
Now using pivot we changed index as year and column as genres and values as count.We filled the nan values for 0.
Cell4:Now plot the graph.Plot the graph with year as x axis and count as y axis and give label as genres.

Challenges and Improvements:
We tried to take our NLP output as data for graph plot but it took a lot of time to run and we got some random errors while converting our data for plot.
So we decided to use the original dataset for graph plotting.
Maybe the popularity chart can be made interactive with pyvis and seaborn.

