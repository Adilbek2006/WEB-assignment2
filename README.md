In this project, I built a dynamic web application using Node.js and Express. The main goal was to create a seamless experience where, with a single click, a user can generate a random profile and immediately see a wealth of related information—including geographical data, live exchange rates, and local news—all aggregated from four different external APIs

How to Set It Up
Install: First, I make sure all dependencies are ready by running:
npm install
Environment Variables: I use a .env file to keep my API keys secure.

COUNTRY_API_KEY
EXCHANGE_API_KEY
NEWS_API_KEY
To start the server, I simply run:
node server.js
Then, I head over to http://localhost:3000 to see the app in action.

The Logic Behind the APIs
I carefully orchestrated the data flow so that each API call builds on the previous one:

Random User API: This is my starting point. I fetch a random person's name, age, photo, and location.

CountryLayer API: I take the country name from the first step to get specific details like the capital city and the official currency.

ExchangeRate-API: Using the currency found in the previous step, I calculate how it compares to USD and KZT in real-time.

News API: Finally, I look for the top 5 news headlines in English that mention the user’s specific country.

My Design Decisions
Security First: I made sure all API requests happen on the Server Side. This way, my sensitive API keys are never exposed to the client's browser.

Clean Code Structure: I strictly followed the rule of keeping logic out of the HTML. My project is organized into clear sections:
server.js: The "brain" that handles all the heavy lifting and API communication.

public/script.js: Contains my frontend logic and DOM manipulation.

public/style.css: Handles all the visual styling to keep the UI clean and modern.

User Experience: I grouped the data logically. For instance, I placed the exchange rates right next to the country info so the user doesn't have to hunt for related details.

Error Handling: I implemented try-catch blocks to ensure that even if one API (like the News or Country API) fails or returns empty data, the rest of the application remains stable and functional.

Dependencies
I used the following libraries to build this:
express: My core web framework.
node-fetch: To handle all external API requests.
dotenv: To manage my environment variables securely.
