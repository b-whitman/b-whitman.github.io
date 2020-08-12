# The Plan

At the outset, as we as a team had the opportunity to explore our vision for where we could take this product, my data science teammates and I conceived of several major features we would focus on: automatic generation of cards and decks from single terms, the use of spaced repetition for efficient memorization, and a selection of user data visualizations.

To accomplish automatic card generation, we used the MediaWiki API to retrieve the beginnings of Wikipedia pages matching the given terms. The biggest hurdle we ran into on this feature was dealing with various edge cases and exceptions that might come into play when taking in actual user-generated data. What should we do if the user put a “the” where there shouldn’t be one? What about minor typos? Singular versus plural? Our overarching goal was to make sure the feature felt as seamless as possible. 

Spaced repetition, by contrast, would happen almost entirely behind the scenes, facing away from the user. Our initial idea was to use a system similar to Anki, where the user rates every card on a three-point scale and the application uses that datum to decide when to next present that card. However, after a team discussion and some user research by the UX team, we decided that implementation could be distracting, asking too much of the user during a study session. So we went back to the drawing board, and landed on the Leitner System, an older implementation of spaced repetition designed for use with analogue flashcards. 

Those analogue origins may have been what made it suitable for our purposes: without a program to calculate next due dates by card, the Leitner System asks only for binary user feedback. Did you get it, or didn’t you? If you did, the card progresses up one level, to be studied less frequently; if not, the card goes back to the first level, which is studied most frequently. We decided to use an existing part of the design, the “star” button, to collect that user feedback. If the user got a card, no action was needed; if they didn’t, they simply clicked the star before moving forward. After a session, the program would tabulate how to move each card, and the next time the user studied, they would see only those cards they needed to.



# The Product

Still forthcoming! Here are screenshots from an in-development deployed build:

# In Retrospect
