# Proximity-Based Supermarket Offers

A web application for discovering, submitting, and validating supermarket offers through an interactive map.

The main feature of the project is proximity-based offer submission. Users can browse supermarket offers on the map, but the option to create a new offer is shown only when the user is within range of the selected supermarket.

---

## Overview

This project is a collaborative supermarket offer platform built with PHP, JavaScript, MySQL, HTML, and CSS.

The application allows users to view supermarket locations, browse available offers, submit new offers, and validate existing ones through likes and dislikes. Supermarkets are displayed on an interactive map, and each marker shows information about the store and its available offers.

The project was developed as part of an academic web development assignment.

---

## Main Feature

### Proximity-Based Offer Submission

The core feature of the application is that users can create an offer only through supermarket markers that are close to their current location.

When the map loads, the application:

1. Detects the user’s current location.
2. Creates a 1000-meter radius around the user.
3. Loads supermarket markers from the database.
4. Checks whether each supermarket marker is inside the user’s radius.
5. Shows the “create offer” option only for supermarkets that are within range.

This makes the offer submission process more connected to real supermarket visits, because users are encouraged to submit offers only for stores near them.

---

## Features

### Interactive Map

The application uses an interactive Leaflet map with OpenStreetMap tiles.

The map displays supermarket locations using different marker colors:

* Green markers for supermarkets with available offers
* Red markers for supermarkets without available offers

Each supermarket popup can show:

* Supermarket name
* Address
* Offer counts by general category
* Link to view the supermarket’s offers
* Link to create a new offer, only when the user is within range

---

### Supermarket Offer Browsing

Users can browse offers in different ways:

* Recent offers from the home page
* Offers for a specific product
* Offers for a specific supermarket
* Offers grouped by category and subcategory

Each offer includes information such as:

* Product name
* Product image
* Price
* Supermarket name
* Supermarket address
* User who created the offer
* Creation date
* Likes and dislikes

---

### Offer Submission

Users can submit a new supermarket offer by selecting:

* Product
* Price
* Note or description
* Supermarket

When an offer is submitted, the system stores it in the database with:

* User ID
* Product ID
* Supermarket ID
* Price
* Note
* Creation date
* Expiration date
* Like and dislike counters
* Out-of-stock status

Offers are created with an expiration date seven days after submission.

The system also checks whether a similar offer already exists for the same product in the same supermarket. A new offer is accepted only if its price is significantly lower than the existing lowest price.

---

### Offer Validation

Users can validate offers by liking or disliking them.

The system keeps track of each user’s activity so that a user cannot repeatedly like or dislike the same offer without updating their previous action.

Likes and dislikes affect both:

* The offer’s total like/dislike count
* The score of the user who submitted the offer

---

### Score System

The application includes a user scoring system.

Users can gain score through useful activity, such as:

* Submitting strong offers
* Receiving likes on their offers

Users can also lose score when their offers receive dislikes.

The user profile page displays:

* Total score
* Monthly score
* Total tokens
* Previous month tokens
* User’s submitted offers
* User’s like/dislike activity history

---

### Leaderboard

The project includes a leaderboard that ranks users based on their total score.

The leaderboard displays:

* Username
* Total score
* Total tokens
* Previous month tokens

This adds a gamified element to the platform and encourages users to contribute useful supermarket offers.

---

### Wishlist

Users can save offers to a wishlist and later view their saved offers from a dedicated wishlist page.

The wishlist page allows users to:

* View saved offers
* Open offer details
* Remove individual saved offers
* Clear all saved offers

---

### User Accounts

The application supports user registration, login, and profile updates.

Users can:

* Create an account
* Log in
* Update their username and email
* Change their password
* View their own activity history

---

### Admin Functionality

The project also includes admin-side functionality.

Admins can access admin pages for:

* Managing products
* Viewing statistics
* Viewing the leaderboard
* Viewing supermarkets
* Using an admin map
* Creating offers from the admin panel

---

## Tech Stack

| Technology       | Purpose                                    |
| ---------------- | ------------------------------------------ |
| PHP              | Backend logic and database operations      |
| JavaScript       | Frontend interactivity and map behavior    |
| MySQL            | Database storage                           |
| HTML5            | Page structure                             |
| CSS3             | Styling and layout                         |
| Leaflet.js       | Interactive map and location-based markers |
| OpenStreetMap    | Map tile provider                          |
| AJAX / Fetch API | Loading supermarket data dynamically       |

---

## Database Structure

The database contains tables for:

* Users
* Products
* Categories
* Subcategories
* Supermarkets
* Offers
* Like/dislike activity
* Score activity
* User tokens
* System tokens
* Wishlist items
* Reviews

Supermarkets store their coordinates in the database, allowing them to be displayed on the map and compared with the user’s current location.

Offers are connected to users, products, and supermarkets.

---

## How the Application Works

1. The user logs in to the platform.
2. The user opens the interactive map.
3. The application detects the user’s current location.
4. A 1000-meter radius is displayed around the user.
5. Supermarket markers are loaded from the database.
6. If a supermarket is within range, the popup includes the option to create a new offer.
7. The user selects a product, enters a price and note, and submits the offer.
8. The offer is stored in the database and expires after seven days.
9. Other users can view, like, dislike, or save the offer.
10. User scores and leaderboard rankings are updated based on activity.

---

## Project Purpose

The purpose of this project is to create a more realistic and community-driven supermarket offer platform.

Instead of allowing users to submit offers from anywhere, the application links offer creation to the user’s current location on the map. This makes the submission process more practical and encourages users to add offers for supermarkets they are actually near.

The project combines web development, database design, interactive maps, user authentication, offer validation, and gamification.

---

## License

This project was developed for academic purposes.
