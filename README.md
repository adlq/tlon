TLON
====

Description:
------------

An application that will be used to track speedsolvers' performances 
during competitions, throughout different events and rounds. Examples 
of such applications can be found at the following websites: 

* [World Cube Association](http://worldcubeassociation.org/results/) 
* [Vietnam Cubing Club](http://rubikvn.org/VCCRP/)

This is my first Ruby on Rails project. My main goal is to apply concepts 
learned in the [*Ruby on Rails Tutorial Book*](http://ruby.railstutorial.org/ruby-on-rails-tutorial-book) 
by Michael Hartl. This could then eventually be used as a newer version 
for the Vietnam Cubing Club website.

Data model:
-----------

* Competition = name:string
		place:string
		time:date
		events:references
		
* Event =	name:string
		


* Competitor =	firstname:string
		lastname:string
		nickname:string
		dob:date
		nationality:string
		location:string
		competitions:references

This is the hard part. In each competition, for each event, 
we must keep track of the order of the single times as well
as the round (1st, 2nd, final) to which they belong. The 
average times must also be kept as recomputing them each 
time a page loads is not scalable. 

* SingleTime =	value:integer (seconds)
		competitor:references	
		competition:references
		round:references
		
* FinalTime =	value:integer (seconds)
