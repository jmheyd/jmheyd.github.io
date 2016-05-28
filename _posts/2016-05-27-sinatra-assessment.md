---
layout: post
title: "Sinatra Assessment for Learn-Verified"
date: 2016-05-27
---

For this project in the Learn-Verified curriculum, we had to build an MVC Sinatra web application with the following requirements:

<ul>
	<li>must use ActiveRecord</li>
	<li>must use multiple Models</li>
	<li>must have at least one has_many relationship</li>
	<li>must have User accounts, and only the user who created the content can modify the content</li>
	<li>must have model validations so that bad data isn't created</li>
	<li>must show validation failures to the user with error messages</li>
</ul>

<h3>What is an MVC Sinatra application?</h3>
<p>Sinatra is a web application library written in Ruby. MVC stands for Model-View-Controller, and it is a programming model that separates these three different parts. So in my Sinatra app, I have an app folder containing three folders: models, views and controllers. </p>

<p>Models - where I define my classes and their associations.</p>
<p>Views - where I determine how the data will be displayed.</p>
<p>Controllers - where I define how the data is read from the view and sent back to the model.</p>

<h3>What is ActiveRecord?</h3>
<p>ActiveRecord is a Ruby library that works with relational SQL databases, in our case, sqlite3. It provides Object Relational Mapping (ORM); a single Ruby object maps to a database table. For example, in my project, College Tour Planner, I have a College object and a College database table.</p>

<h3>Multiple Models</h3>
<p>My project has a College model and a User model (and a model that joins them).</p>

<h3>The has_many relationship</h3>
<p>In my project, a user is making a list of colleges they would like to tour to help in deciding which college they would like to attend. A user can have many colleges on their list. Also, a college can have have users who add the college to their list.</p>

<h3>User Accounts</h3>
<p>Users must sign up and create an account to create a college list. Nobody else can view their list or modify their list. In addition, users may leave notes about each college that only they can view, edit or delete.</p>

<h3>Data Validations</h3>
<p>A user must enter all the proper information to create an account. When adding a new college to the database, all fields in the form must be filled out.<p>

<h3>Error Messages</h3>
<p>Error messages will appear on the screen if a user doesn't complete the sign up correctly, or if they don't fill out the college form completely. In addition, error messages will appear if a user tries to view or edit another users's content</p>

<h3>Challenges</h3>
<p>I spent a long time thinking about this project before I actually started coding. I knew I wanted a user to be able to log in and select from a list of colleges to visit. They needed to be able to update their list. In addition, I wanted the user to be able to take notes about that college; maybe reasons why they liked the school or facts they wanted to remember. This concept of the note and how to model it introduced the biggest challenge for me.</p>

<p>I knew I would need a User model and a College model. In addition, I'd need to model the association between the two models: Users could have many colleges and colleges could have many users. I stumbled thinking about how the notes fit into this. Did I need a note model? Did I have to call the "join table" UserCollege? or could I call it something else? What I decided to do was model the object UserCollege which mapped to the table user_colleges. This user_colleges database table contains the columns for id, college_id, user_id and then note. Since I just wanted the user to have one note per college, this seemed like the way to go. But the whole time I worked on this project, I wasn't sure if this was the best way to model everything. And I really wanted to call it the Note model, not the UserCollege. I'm still not sure I did this the best way</p>

<p>The next challenge was just not getting confused in all the routes. There is a lot of back and forth, and sometimes it got confusing to keep it all straight.</p>

<p>When I finally got it working, I was grateful for the additional HTML/CSS classes I had taken with Girl Develop It! (GDI) Minneapolis. The templates and files I got from those classes helped me add some of my own style to my web application</p>