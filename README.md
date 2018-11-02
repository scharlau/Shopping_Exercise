# README for the Shopping Exercise #

This is a 'deliberate practice' exercise for working with Rails. As before, the goal here is to have an example that lets us better understand one part of a Rails application, and not to have a perfect example. To that end this shopping example is purely for exploring relationships.

This example is a simplified and modified version of the 'Depot' example found in "Agile Web Development with Rails" from Pragmatic Programmers (https://pragprog.com/book/rails5/agile-web-development-with-rails-5) We're using this example, because it lets us quickly get to the relationships that we want to explore. This example also uses the Faker Gem from https://github.com/stympy/faker to generate sample data for the application.

## Setting Up the Exercises ##

Pull the Git repository via download, or by cloning to your computer. Run

    bundle install

To get all of the gems sorted. Now run the migrations with either rails or rake command depending upon your platform.

    rails db:migrate

This will set up your database, and now you can run the seed_tables script to populate your database with the command:

    bin/rake products:seed_tables

This will generate data using the Faker gem that we can use in the exercises.
After you start the rails server you can now see the following items in the application:
* localhost:3000/customers
* localhost:3000/products
* localhost:3000/line_items
* localhost:3000/orders

In their current state the line_items and orders pages are not very helpful, because they show Class objects where you'd expect to see a customer name, product name, or cart_id, although actually you don't need to ever see the cart_id, because it's only used as a staging area for the shopping cart.

In this example the shopping cart doesn't work. That's something that I'll fix in a future update. For now it means you should not create cart objects as they will not show up on the page.

## Do the Work ##

Work through the three rounds with a partner, or on your own, depending upon your circumstances. Each round should be twelve minutes, followed by a discussion of where you are and what has been working, as well as, what you're working on next.

You may want to refer to the shopping/db/schema.rb file to better understand the database schema before you get started. Some of you might even want to diagram the schema.

1. Round one should be fixing the line_item and order pages to show names of items and customers.
2. Round two should be creating a 'dashboard' page to show total orders ranked by customers.
3. Round three is making round two work when you scale up the database by changing the numbers in the seed_tables files to work with 50 customers and orders of 10 items per customer, or by setting it up so that you also have customers, who have no orders.
