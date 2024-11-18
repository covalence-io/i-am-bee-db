# IMBDB

## A.K.A. I'm (the) Bee Database

This is a fully fledged full-stack app _without_ auth yet for students to get some extra auth practice.

It maintains a list of user accounts, a list of bee species, and users will create log entries out bee sightings. This app is like a semi-private journaling site where all posts are visible to all users, but you must be a registered and logged in user to see posts.

## Getting Started

-   Run `npm install` to get your dependencies

-   Grab the script at [starter.sql](./starter.sql) to create the tables and pre-populate them with some data (the 1 user account for Buzz Lightyear has a plaintext password of `password123`);

-   Copy the [.env.sample](./.env.sample) file to a new `.env` file, filling it out with _your_ database user and database password.

-   Take a look around the backend, especially in the routes and queries. All the queries are fully written and you won't need to add or alter any (for the base requirements). Your work with routes will only be within the auth routes folder.

## Backend steps

-   Import all the passport libraries & their types, then create your passport middlewares

-   In the auth routes folder, develop your login and registration routes, using bcrypt to salt+hash your passwords, and jsonwebtoken to sign and issue tokens (make sure to update your `.env` and config accordingly!)

-   Protect _all_ your API routes, and in the process of doing that, ensure that any hardcoded placeholder `user_id` values in routes are getting derived from the _user_ making the _request_ instead

-   **BONUS** - as the requirements stand, all it takes to update or delete a sighting entry is that you're a valid user with a legitimate, unexpired token. You can edit my posts, and I can delete yours. There are a couple of different ways you could validate this - one would involve editing the WHERE clause of the update & delete queries to include an extra bit of data, and the other would involve preemptively getting that item and making sure some properties of it align with the user making the request. Try it out!
