# README

** Shopping Exercise **

This is a 'deliberate practice' exercise for working with Rails. Pull down the Git repository via download, or by cloning. Then work through the three rounds with a partner, or on your own, depending upon your circumstances. Each round should be twelve minutes, followed by a discussion of where you are and what has been working, as well as, what you're working on next.

As before, the goal here is an example that lets us mess around to understand one part of a Rails application, and not to have a perfect example. To that end this is purely for exploring relationships.

This example is a simplified version of the 'Depot' example found in "Agile Web Development with Rails" from Pragmatic Programmers (https://pragprog.com/book/rails5/agile-web-development-with-rails-5) because it lets us quickly get to the relationships that we want to explore. You can use these commands to build this up from scratch yourself if you like, or just download the repository and start from there.


rails generate scaffold Customer name email address

rails generate scaffold Product name price:decimal

rails generate scaffold Cart

rails generate scaffold LineItem quantity:integer product:references cart:belongs_to

rails generate scaffold Order customer:references

rails generate migration add_order_to_line_item order:references

With these in place we can modify a few of the models to finalise the relationships.
