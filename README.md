# README for the Shopping Exercise #

This is a 'deliberate practice' exercise for working with Rails. The goal is to have an example that lets us better understand one part of a Rails application, without having to build something from scratch. To that end this shopping example is purely for exploring object relationships.

This example is a simplified and modified version of the 'Depot' example found in "Agile Web Development with Rails" from Pragmatic Programmers (https://pragprog.com/book/rails5/agile-web-development-with-rails-5) We're using this example, because it lets us quickly get to the relationships that we want to explore. This example also uses the Faker Gem from https://github.com/stympy/faker to generate sample data for the application.

In this example the shopping cart doesn't work. That's something that I'll fix in a future update. For now it means you should not create cart objects as they will not show up on the page.

That still leaves lots of other parts that can be made better in this application. 

## Setting Up the Exercises ##

Step 1) Pull this Git repository via download, or by cloning to your computer. If you're using Cloud 9 on AWS, then save to your machine, and then upload it to Cloud 9.

Step 2) Open a terminal and cd into the 'shopping' directory, open a console and run

    bundle install

This will install the gems for the application. 

Step 3) This app has tables so we need to run the migrations to set up the tables.

    rails db:migrate

This will set up the tables in your database.

Step 4) Now you can run the seed_tables script to populate your database with the command:

    rake products:seed_tables

This will generate data using the Faker gem for the application, which we can display in our exercises.

Step 5) Start the server and look at your app. 

Step 6) After you start the rails server you can now see the following items in the application:
* localhost:3000/customers
* localhost:3000/products
* localhost:3000/line_items
* localhost:3000/orders

The customers and products pages are ok. You can ignore these for this exercise. 

Focus on the line_items and orders pages as you do the exercises below. The line_items ane orders pages need your help. These show Class objects where you'd expect to see a customer name, product name, or cart_id. Actually, you could remove the cart_id. Users never need to ever see the cart_id, because it's only used as a staging area for the shopping cart. 

## Do the Work ##

Work through the three rounds with a partner, or on your own, depending upon your circumstances. Each round should be twelve minutes, followed by a discussion of where you are and what has been working, as well as, what you're working on next.

You may want to refer to the shopping/db/schema.rb file to better understand the database schema before you get started. Some of you might even want to diagram the schema. You might also want to spend a few minutes at the start of each round planning what you might want to do.

1. Round one should be fixing the line_item and order pages to show names of items and customers.
2. Round two should be creating a 'dashboard' page to show total orders ranked by customers.
3. Round three is making round two work when you scale up the database by changing the numbers in the seed_tables files to work with 50 customers and orders of 10 items per customer, or by setting it up so that you also have customers, who have no orders.
