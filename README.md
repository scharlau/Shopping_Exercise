# README

** Shopping Exercise **

This is a 'deliberate practice' exercise for working with Rails. As before, the goal here is an example that lets us mess around to understand one part of a Rails application, and not to have a perfect example. To that end this is purely for exploring relationships.

This example is a simplified version of the 'Depot' example found in "Agile Web Development with Rails" from Pragmatic Programmers (https://pragprog.com/book/rails5/agile-web-development-with-rails-5) because it lets us quickly get to the relationships that we want to explore. You can use these commands to build this up from scratch yourself if you like, or just download the repository, skip down to the 'Exercises' part of this file, and start from there.

** Build this yourself **

rails generate scaffold Customer name email address

rails generate scaffold Product name price:decimal

rails generate scaffold Cart

rails generate scaffold LineItem quantity:integer product:references cart:belongs_to

rails generate scaffold Order customer:references

rails generate migration add_order_to_line_item order:references

With these in place we can modify a few of the models to finalise the relationships. Check the repository to see what was added to the models and controllers.

We also want to generate fake data by using Faker Gem. Add this line to the 'development, test' group in the Gemfile:
gem 'faker'
Then we generate a task file with the command:

    rails g task products seed_tables

This will let us create a script in the generated file (lib/tasks/products.rake) to fill our tables automatically, so that we can then play with the relationships.

** Do the Exercises **

Either build this as above, or just pull down the Git repository via download, or by cloning. Then run the script to populate your database with the command:

    bin/rake products:seed_tables

This will generate data using the Faker gem that we can use in the exercises.
You can now see the following items in the application:
localhost:3000/customers
localhost:3000/products
localhost:3000/line_items
localhost:3000/orders

In their current state the line_items and orders pages are not very helpful, because they show Class objects where you'd expect to see a customer name, product name, or cart_id, although actually you don't need to ever see the cart_id, because it's only used as a staging area for the shopping cart.

Then work through the three rounds with a partner, or on your own, depending upon your circumstances. Each round should be twelve minutes, followed by a discussion of where you are and what has been working, as well as, what you're working on next.

1. Round one should be fixing the line_item and order pages to show names of items and customers.
2. Round two should be creating a 'dashboard' page to show total orders ranked by customers.
3. Round three is making round two work when you scale up the database by changing the numbers in the seed_tables files to work with 50 customers and orders of 10 items per customer, or by setting it up so that you also have customers, who have no orders.
