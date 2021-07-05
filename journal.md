# Day by day journal 

*In this journal you will find sum ups of my work each day* 

### 10/05/21:

First day of my internship. We discussed the tasks and goals related to my internship. 
The internship is divided in 2 parts :

* First, the Web application the consist of a learning environnement where a language/linguistics teacher can choose from different tags and properties to auto-generate an exercice corresponding to some learning goals. 
For the Web app we use the Python Flask framework. However the previous app was coded in Php-laravel which we now find kind of unnapropriate so we want to migrate all of the previous app content to a Flask version. 
The front-end of the app represents the "student's side". This part also uses Ajax for a dynamic and immadiate correction of the student's answers. 
The back-end side is the "teacher's side" where they can decide the parameters of the exercice. 


* The second part (reseach part) consists of creating/defining a model that can tackle the grammatical features of the texts used by the teachers and labels those grammatical features. An approched we discussed could be to consider blocs (S-V-O in French for example) within the sentence instead of the word itself to find out the grammatical relationships that exists between them. 

---

**TO DO THIS WEEK** 

- [ ] Initialize the Trello board
- [ ] Do the ![OpenClassroom's](https://openclassrooms.com/fr/courses/4425066-concevez-un-site-avec-flask/) tutorial on Flask. My repo is ![here](https://github.com/MathildeAguiar/FlaskTutorial)

--- 

Part 1 of the tutorial is done. 



### 11/05/21:

* I keep following the OC Falsk tutorial. I almost finished reading it all (except the chapter dedicated to Facebook and the last 2 ones). 
* I created the website up to chapter "découpez votre projet en templates". However it's still messy and need to be cleaned up.

---

**TO DO TOMORROW** 

- [ ] Finish the website dev according to the OC tutorial and use all the facebook features she displays on the tutorial.
- [ ] Fill up the Trello. 
- [ ] Think about a generic website model that could fit our project and start to build up the architecture.

### 12/05/21:

* I decided to start again from the beginning the coding of the OC tutorial's website. I cleaned up the code and encountered a few (stupid) bugs. I just need to set up all the facebook stuff and it will be done. 


### 13/05/21: 
*holiday but couldn't help to touch the code*

* Added a few changes to the new website version. 
* Found out that the facebook authentification couldn't be done because of non https adresses that no longer supported. However, specified in the FB documentation localhost should work anyway. Still trying to figure out this bug. This thing keeps me from testing my full website which is really frustrating. 
 
### 14/05/21:

**TO DO TODAY** 

- [ ] Finally filling up that Trello and watch vids/read docs about how Kanban really works
- [ ] Still looking for the fb authentification bug
- [ ] Sketch a new website interface 

--- 
Facebook **troubleshooting** :
Facebook only works with https URL since 2018. However my Flask application uses the classical http form of the localhost. I need to enable the https version of my local host. To do so I found a solution ![here](https://blog.miguelgrinberg.com/post/running-your-flask-application-over-https). To sum up I just need to change the **app.run()** in my run.py file and add the argument **ssl_context='adhoc'** . However, with just this argument we have a security problem message from the web browser. To solve this problem we can generate a self-signed certificate with openssl. Use the command: `openssl req -x509 -newkey rsa:4096 -nodes -out cert.pem -keyout key.pem -days 365`
Then modify again the **app.run()** args with:
`ssl_context=('cert.pem', 'key.pem')`

Well, it seems to not work well for now. I still have the same URL problems.

### 17/05/21:

I read the doc about Flask-WTF, bootstrap-flask and SQLite. I used the sample SQLite ![database](https://www.sqlitetutorial.net/sqlite-sample-database/) to develop a little website where you fill up a form (using flask-wtf) that can browse through the sqlite sample database. I used the following ![tutorial](https://hackersandslackers.com/flask-wtforms-forms/) for the wtf form. 
So far, I did the form, howerver the sql queries are still missing. I must finish to set up the whole database (sqlachemy part) and write the queries.   
I must set up the bootstrap part. 

---
**TO DO TOMORROW**

- [ ] set up the bootstrap
- [ ] write queries
- [ ] finish to set up the database

### 18/05/21:

Meeting with Yannick this morning. 
The result page is fixed and the database is set up. I need to finish the queries and set up the bootstrap. 

### 19/05/21:

* I set up the bootstrap Flask on my Collection de Disques website. Now we have a beautiful form.
* I messed up with the database (I defined the database like SQLAchemy one instead of a SQLite one) so I have to redo that.
* I made some prototypes of the ihm we want for our final application
* I started to setch an architecture of the files needed to create the final application

### 20/05/21:

I worked on the database again. I had troubles with the queries and the database so I worked on that part.

### 21/05/21:
The database is set and so the queries. I still have to do a few ajustments in the way it appaears on screen.

### 25/05/21:

Meeting with Yannick. I showed my current version of Collection de Disques. We decided that I will keep working on this but with transposing the chinook database into what our final application could look like. 

---

**TO DO THIS WEEK**

- [ ] Use the chinook database as a reference to keep working on the collection de disques website. Be careful on how we could use it to do a transposition to the final website.
- [ ] Keep working on the interface sketches.
- [ ] "Test" my interfaces on my teacher mom to see if it would be easy to use  

* I transposed the chinook database for our use with teachers. 
* I sketch 2 more interfaces. 

*I forgot to update it here oops*

### 26/05/21:

* I started working on the bootstrap part. I tried different options but I still struggle to get what I want. 
* I added new queries corresponding to some teacher's needs. I want to display the results in a table using **render_table()** from bootstrap flask. However I still need to manage it properly.

### 27/05/21:

* I changed some things in my mock-ups. I added some few animations. Almost all the mock-usps first version are ready to get tested by the teacher.
* Still managing the way bootstrap side navs are displayed.

### 28/05/21:

* I cleaned the code with a better architecture.
* I'm still trying to display the bootstrap the way I want with using at most the bootstrap flask.
* I finished the first animated/linked version of the mock-ups. Testing them on the teacher this Sunday.

### 31/05/21:

* I changed some queries and I displayed the results in better shape than before.
* I tried different ways to use bootstrap.
* I had feedback from the teacher yesterday. I did a few adjustments to the mock-ups. 

### 1/06/21:

Meeting with Yannick. We discussed about some adjustments about the future interface. We decided that I will be doing the following work this week:
- [ ] From the previous search form that I did on chinook, design a search form where the teacher could look for "anything" they want, a free search form.
- [ ] Design the questions validation interface with a table where we could modify/approve/disapprove the question found by our engine.
- [ ] Design the interface for the exercise editing.

* I finished creating my base (header/footer/nav) for all pages. Finally clean! 

### 2/06/21:
* I created the different forms and pages needed. I still have to improve the overall aspect but we have a nice base. I am waiting for the database extract to continue to work.  

### 03/06/21:
* I receive the database extract but I didn't really started working with it. I fixed some issues on the bootstrap aspect. 
* There is still a problem remaining with the use of some incons with render_icon from bootstrap flask. I think I'll need to get them with the svg or something.

### 04/06/21:
* I started initializing the database with some data I wrote really basic queries. 
* I hard a hard time with circular imports. I'm still troubleshooting it which is really annoying because I can't test anything.

### 07/06/21:
* I fixed the circular import porblem!! I can test now! 
* I changed the notions validation page aspect
* I fixed some queries for the exercice creation page
* I'm working on the "search anything" query 
* I have nice tables displaying the results of my queries 
* I still need to clean the code and change for dynamic select fields in the forms 

### 08/06/21:
* Meeting with Yannick : we dicussed about some details, he explained me some aspects I didn't catch up well and I presented him my current work.
* I fixed some visual/bootstrap problems. I have a much cleaner and responsive interface now. 
* I still have to deal with the navigation and the languages/translations of pages. I looked up for Babel Flask 

### 09/06/21:
* I created some dynamic choices fields with mockup values. I still have to refine the database to match the exact categories needed in the forms' fields.
* I drafted some new tables for the database but I didn't displayed them in the code yet. 
* I coded queries for the home page and a category field to fine-tune the research. I'm still not satisfied with it yet, I would like a checkbox visual instead of a list but for now I get a messy result. 

### 10/06/21:
* I changed the queries but it's still messy. 
* I tested a way of dsplaying CheckBoxes for choices. 
* I tested to change the query for the home page with adding a LIKE feature. 

### 11/06/21: 
* I tested Babel Flask on a small website to understand how it works. 
* I started dealing with the effect on click for displaying the notions 


## 14/06/21:
* Meeting with Yanick: I have to redesign my own version of the database. I will also set up the Babel Flask in English.  
**TO DO THIS WEEK**

- [ ] Redesign the whole database 
- [ ] Populate the new database 
- [ ] Rewrite all my queries according to this new database
- [ ] Translate in english with Babel Flask

### 15/06/21:
* I sketch the new database configuration (still some improvments needed)
* Coding the new database tables with SQLAlchemy

### 16/06/21:
* Populated the database with some data I extracted from the previous Nicolas' database.
* Troubleshooting the issues coming from the new database configuration and adapting my old queries to this new db.  
* Fixing some visual details. 

### 17/06/21:
* Modified the side nav with dynamism of the chapters avaible (still have to link it to the user session but I'll see that part later)
* Fixing some queries. All queries written since today works perfectly fine ! 
* Adding dynamism for the list of exercices shown in function of which chapter they're related to. *Still working on this*

### 18/06/21:
* I fixed my side nav and I even created the "groupes" and "Aide" pages. Now all elements in my side nav works great. 

### 21/06/21: 
* Fixes of some bugs and cleaned a bit the code

### 22/06/21:
* Meeting with Yannick : we idscussed about the database and what to keep/change/remove. Looked at the interfaces.

### 23/06/21:
* Starting correcting the database composition. Correcting the queries in consequence.

### 24/06/21: 
* Still working on the database structure but I'm still struggling to make some choices in its configuration. 
* Changed some forms and associated queries. 
* Did some queries for editing/deleting a notion on the validation page but until the db is unstable it's not quite efficient.

### 25/06/21: 
* I changed quite a few details in the existing interfaces. Added a dashboard to the home page to access more easialy to all pages. 
* I added a page to create some exercices sessions. 
* I'm starting to visualize the overall of the website pages which makes it easier to refine my database configuration !  

### 28/06/21:
* I keep correcting the database configuration. I still don't know if this configuration is great but I'm trying to find something correct.  

### 29/06/21:
* Meeting with Yannick we discussed about the database again. We changed a few things and he mainly agreed on my actual configuration. 
* I changed some details in the db implementation thanks to Yannick's suggestions.

### From 30/06/21 to 02/07/21:
* I debugged the problems that came from the things I changed in the db implementation. 
* I started brainstorming an interface where the teacher can manage the student's results to exercises sessions and chapters. Still in progress. 
* I changed some details in the forms previously created and some other details in other interfaces. 

### 05/07/21:
* Creating new queries for addind/modifying/deleting sessions/chapters/exercises. The difficulty stands in managing correctly many to many relationships.
* Finish the design of the students' results/progress interface.
