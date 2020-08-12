# The Plan

I combined a dataset I’d already collected from IMDb, which contained all movies in their database, with box office and budget data from www.the-numbers.com. I removed movies from before 1975, because I couldn’t think of a clean way to adjust for inflation. My plan was to train an XGBoost regressor on the dataset, with budget, release month, runtime, user score, and genre information as the features, and box office take as the target. I realized after some testing, however, that user score was very leaky. The studio planning a funding and release schedule for a given year would not have access to user ratings of their movies. I didn’t want to drop the feature entirely, however, so I abstracted it into a binary “hype” feature. Movies in the upper quartile by user score were designated “hyped,” and “hype” did in fact seem to be one of the better features for predicting box office.

# The Product

https://see-you-at-the-movies.herokuapp.com

My biggest aim for this project was to surface my predictive model as a sort of data toy, so an interested user could design their own movie and see how it would do at the box office. 

# In Retrospect

In looking back at this project, I feel I learned a lot. I leveraged machine learning on a natural dataset. I engineered a functioning front-end to explore the data. And I felt confident enough to draw some tentative conclusions about patterns I spotted. Even so, hindsight has granted me some perspective on limitations to the project, and since completing it I have come up with some ideas of how I might approach it differently if I revisited it.

The biggest change I would make is to make this tool more useful for the actual movie business, and take into account a movie’s budget when determining how successful it actually is. I believe studios care less about how much money a movie takes in at the box office, and more about what the return on investment is. So rather than training my model to look at the raw box office, it might be more interesting to subtract a movie’s budget from its earnings and train my model on that ROI. I could even divide that by the budget to get a percentage and normalize the data somewhat, to get a clearer picture.

Apart from that, a few limitations have come to mind since completing this project. With the COVID-19 pandemic have come many changes to our daily lives, and changes to many industries, including the film industry. Movie theaters may not go back to normal for years, if ever. Into that entertainment gap will slide streaming services, offering access to many titles for a flat subscription fee. And with that change, I believe it’s fair to expect box office revenue to decline in importance as a ubiquitous marker of success. Streaming numbers will become more important, as will each services ability to serve up the specific content their users crave. This opens up the way for online entertainment storefronts to leverage machine learning in their recommendation engines in fascinating and creative ways. Look no further than Steam and Spotify for examples of storefronts already incorporating some of these possibilities. But the humble regression model may find itself of limited use in this brave new world.
