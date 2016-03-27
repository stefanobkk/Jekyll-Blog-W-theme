---
layout: post
title:  "Internet Programming Finals Notes!"
cover: cover.jpg
date:   2016-03-26 21:52:45 +0700
---

# Rails Structure

**App** So the app folder is used to store the majority of what you will be doing inside of rails. It contains folders that hold the web-applications *view*, *assests*, *controller*, *models*


**Config** The majority of the time you will be editing two files *routes.rb*


### Rake Commands

* **rake db:create** # Will create a databse form DATABASE_URL or in rails its config/databse.yml
* **rake db:drop** will get rid of all the data inside the database and to be able to use it again you need to do a rake db:migrate to put all associate all the tables back to yor site.  
* **rake db:migrate** adds the migration to your project for example you just added another column to your database. You need to migrate it before it will be in your rails project.   
* **rake db:migrate:status**
* **rake db:reset**


### Socket

* **Polling** is the continuous checking of programs or devices to see what state they are in, ussually to check if you are still connected. This is somewhat an old way to check the devise or program status as the CPU is much faster than the I/O and will have to keep waiting for status to change. Interrupt is an alternative to polling. 
	* The CPU can determine how often it need to poll.
	* Ask's the servers in intervals	  
* **Long Polling** is similar to polling but instead of asking the server in intervals if it's done it keeps the connection line open and waits till the server has new data before requesting. This way we are not wasting the CPU

* Difference between Port and Socket
	* A socket is one of two endpoints in a connection between two computers. 
	* A Port is a part of an adress by which a socket link can be established. An example of this is that one machine has one IP adress but can have multiple ports
	* Eg. The port in Jekyll defaulted at 4000 whilst rails is at 3000



# Security 

### Protecting against cross site scripting(XXS)

* Cross site scripting is one of the easiest ways for you to get sensative data pulled from your site. 


### SSL 
* Secure Socket Layer is a security technology that alows you to establich an encrypted link between server and client. 
* Good when you want to transmit sensative data such as credit card number, emails

**How Can You Tell If Site Is Secure?**

* In most updated browsers you should be able to see a green lock symbol 
![alt text](http://i.stack.imgur.com/Vr8IB.png "SSL Verification lock icon") somewhere along your url. If the site you are visiting has a green lock symbol it means that its secure.
* Can also notice that the url starts with **https** instead of **http** 


**How Does it Work**

1. Browser wants to load google.com what it does is it ask the server to respond, identify itself

2. The server that has SSL protection send out a public key to the browser so they can form a 'handshake' or a secure connection 

3. The browser then has to verify that the public key given is still valid. This is done by checking it against CA. 

4. Server decrypts the public key using its private key 

5. Connection secure. 


**Session Hijacking**
Is when an attacker is able to steal the session id (eg.cookies) and able to surf the web as the person who got their session id stolen from. 

* This is usually able to happen when the user is not browsing on a page that does not have SSL. Thats why its better to store your site behind an HTTPS.

* Can only go so far HTTPS protects you from people seeing your credentials but the user's session is still vulnarablee.

* Devise gem is susceptible to session hijacking but rails has set up certain protocols to help such as 
	* Use secure cookies 
	* only send cookies thorgh HTTPS

* In rails you can go to config/application.rb and add 
	* config_force_ssl = true


**Session Fixing**

* Session fixing is a very deadly attack and works by trying to gain access as another user, hopefully a user that has a lot of privileges. 

* How it works is that the attacker will try and gain access to a users session ID in a cookie. What this then allws them to do is start to browse as the other user and if they have enough privileges can take some sensative information. 

* Tokens used for form varification is another vulnerability

* Can protect youself by always resetting your user session 
	* reset_session
	* Set expirety time on the token's so a user woul have to sign back in after being idle for more than 10 minutes.


**Cross-site Request Forgery(CSRF) Attacks**

**Redirection**

* This type of threat is very real and I personally have had my account phished by clicking on an unsafe link.

* The difference between the original(safe) link and the unsafe link can be very minimal. 

* They do this by posting a link of your page and your other users clicking on it. Some attackers will even model their fake sike to look indentical to yours so you can't tell the difference. 


**Brute Force**


