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
