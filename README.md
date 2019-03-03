# halostats
A repository for my Halo 5/6 Stats Web Application built using Go, React, and Docker

Halo 5/6 Stats Website with GoLang, React, and Docker

Purpose:
I am wanting to learn more about Go, React and Docker. 
I haven't had much exposure to these technologies at work so a project like this will be motivate me to learn the ins and outs of these technologies.
This will be a great project to showcase to potential employers and will also be a fun way to learn. 
This stats app will provide fun statistics about your Halo gameplay that you can't get anywhere else.

Go Back-end:
-- Pull stats from the API using REST calls
-- Will need JSON serialization
-- Will need to build a REST API that can be called by React
-- Stores stat data into a database
-- Processes advanced math and algorithms to output interesting stats
-- Consider separating various components into entirely different packages that can then be used as individual Docker containers


React Front-end:
-- Primarily JUST a front-end. The goal is to have React do as little of the logic for the app as possible.
-- Will call Go back-end's REST API to get data to serve to webpage
-- UI should work on mobile and desktop without issue
-- Hopefully can be designed to be a single-page application...


Web Server:
-- NGINX? 


Docker Integration: 
-- Designed so that development and production Docker environments are identical
-- Front-end and back-end are isolated to their own respective containers, allowing updating of individual components
-- Consider putting different Go packages into separate containers to allow for updating individual components


Database Considerations: 
-- Leaning towards Postgres since I know it and it's fairly easy, will research others though
-- Will Postgres be its own Docker container?
-- Relation or not? 
-- Does Go work better with a certain DB technology over others? 
-- Does Docker work better with a certain DB technology? 
-- Does React work better with a certain DB technology? 

--- If all three work best with a different DB tech, who gets priority? (Probably Go since it's handling the bulk of the databaase building operations)


Additional Considerations:
-- Host using AWS or Azure?


First steps: 
1. Learn GoLang
	a. Finish the Little Go Book
	b. Read/consume more advanced learning materials
		- Knowledge needed:
			1. multi-threading
			2. REST calls
			3. JSON serialization
			4. Building a RESTful API for React
			5. Database reading/writing
			6. Docker containerization
2. Learn Docker and Docker-Compose
	a. Pluralsight courses?
	b. Ask Daniel again about best Docker learning materials
	c. Questions about Docker that need answering:
		1. Can each Go package be its own container? Does it make sense to do it this way?
		2. If using GoDaddy or similar service, how do you deploy Docker?
		3. Does Docker run the webserver? (Nginx or similar)
		4. Will Postgres be its own Docker container?
		5. Will the React front-end be its own Docker container?
		6. Do I need to setup an artifactory? What is an artifactory?
3. Learn React
4. Learn Postgres
	a. I know how to use Postgres but how do I...
		1. Get Go to talk to Postgres?
		2. Get React to talk to Postgres?
		3 Containerize Postgres?
		
		
What will the Go back-end do?
-- Make REST calls to the Halo stats API
	-- multi-threaded calls
-- Serialize the JSON responses into objects (are objects a thing in Go?)
-- Write pertinent data to the Postgres DB
	-- this will require multi-threading since the number of games can easily be in the thousands and players won't want to wait forever for their data
-- Have a RESTful API that can be called by the front-end
-- Process stat data, for example:
	-- Number of betrayals
	-- Team mate / Enemy killed the most
	-- Team mate / Enemy played the most
	-- Average life span
	-- Average damage dealt
	-- Have you played against anyone famous or a 343 employee?
	-- Do you do better or worse when playing with a certain player?
	-- <more here>
-- Handle auth? Do I want there to be auth? Should this be handled by React?
-- Run automated tasks that check for new match data nightly? Can this be done? Similar to a cron job
