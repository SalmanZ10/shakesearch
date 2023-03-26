# ShakeSearch

Welcome to the Pulley Shakesearch Take-home Challenge! In this repository,
you'll find a simple web app that allows a user to search for a text string in
the complete works of Shakespeare.

You can see a live version of the app at
https://pulley-shakesearch.onrender.com/. Try searching for "Hamlet" to display
a set of results.

In it's current state, however, the app is in rough shape. The search is
case sensitive, the results are difficult to read, and the search is limited to
exact matches.

# Implemented Features

## Web

- Highlighted text in every result item for better visibility
- Implemented pagination with current page ranges for better user experience
- Added result index for easier identification of the result item (which may be replaced with showing the SCENE in the future)
- Implemented cached API responses to reduce server costs and speed up the process
- Highlighted text in every result item for better visibility
- Implemented pagination with current page ranges for better user experience
- Added result index for easier identification of the result item (which may be replaced with showing the SCENE in the future)
- Implemented cached API responses to reduce server costs and speed up the process

## Backend
- Text length can be greatr than 250
- Implemented Pagination in API


## Local Setup

Requirements:
1. go version = go1.19.7
2. node --version = v16.10.0
3. npm --version = 7.24.0

Steps:
1. npm run build
2. cd backend 
3. go build main.go
4. ./main
5. npm run start

# Decisions and tradeoffs

I have make tradoof between pagination and infinite scroll while listing items and chose pagination because infinite scroll can make it difficult to find results, especially on mobile devices. It also makes more sense when searching through the script as users typically search by sections. In the future, the I can to speed up server processing time by providing clear ranges and reducing memory costs.

Initially, I have implemented pagination on the server side. However, since the scope of the script is small, and showing too many results on a page wouldn't make sense, it's faster to do pagination on the client side. In case the scope increases in the future, it would be better to do both client and server-side pagination.

if this were a bigger project, I would extract the text and important filters and save them in the database to improve search functionality. and also add cache on the server side, improve the UI/UX by remembering search results, increase test coverage for edge cases, and dockerize the project for team collaboration.