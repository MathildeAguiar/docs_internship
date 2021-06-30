# Difficulties 

*In this file I'll make an inventory of problems I've encountered during my internship*

## Flask and URLs with arguments :

I wanted to use arguments with my routes in the views.py file. At first, I tried to redefine another @app.route and a whole bunch of a new code. But since I'm lazy and hate rewritting useless code I found out this ![solution](https://stackoverflow.com/questions/7478366/create-dynamic-urls-in-flask-with-url-for).



## Database design :

One of my biggest difficulty was to design the database. I had a hard time visualizing all the components/interfaces I needed for the application. 
To help myself out I first wrote a text of interactions and how a user would use our application. I inspired myself from the Base de Données' exam where the teacher gave us a text (the client wishes) and we had to draw an UML graph out of it.
So I did exactly the same. I read my Database courses from S7 and wrote the UML graph on **paper**. Then I looked for throught SQLAchemy documentation to understand how to code my db correctly.
I put a particular attention to the ![relationships](https://docs.sqlalchemy.org/en/14/orm/basic_relationships.html?highlight=association#many-to-many), since the previous database model was not including much of them.

