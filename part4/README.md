# 🌐 HBnB – Part 4: Simple Web Client

# Overview 🏗️

This stage focuses on building the front-end client for the HBnB application using HTML5, CSS3, and JavaScript (ES6).
You will create an interactive user interface that communicates with the backend API developed in previous parts, enabling a complete full-stack experience.

# Key Features 🔹

🎨 Responsive UI based on provided design
🔐 User authentication (login system)
📡 API integration using Fetch/AJAX
🏠 Display list of places
📄 View detailed information about a place
✍️ Add reviews (authenticated users only)
🍪 JWT token storage using cookies

# 📆 Project Structure

web_client/
├── index.html
├── login.html
├── place.html
├── add_review.html
├── styles/
│ └── main.css
├── scripts/
│ ├── login.js
│ ├── places.js
│ ├── place.js
│ └── review.js
└── README.md

# 🧠 Key Concepts Implemented

✅ HTML5 semantic structure
✅ CSS3 styling and layout
✅ JavaScript ES6 (modules, fetch, DOM manipulation)
✅ API communication using Fetch API
✅ JWT authentication & session handling (cookies)
✅ Client-side routing & redirection
✅ Dynamic rendering without page reload

# ⚙️ Getting Started

🔹 Open the project
You can run the client directly in the browser:
open index.html
Or use a simple local server (recommended):
python3 -m http.server 5500
Then visit:
http://localhost:5500

# 🔐 Authentication

Users log in via the login page
JWT token is stored in cookies
Protected actions:
Adding reviews
Accessing certain pages
Unauthorized users are redirected to login page

# 📡 API Integration

Uses Fetch API to communicate with backend
Includes:
GET → fetch places / place details
POST → login / add review
Sends JWT token in request headers:
Authorization: Bearer <token>

# 📄 Pages & Functionality

🔹 Login Page
Authenticates user via API
Stores JWT token in cookies
🔹 Places List (Home)
Fetches all places from API
Displays them dynamically
Filters places by country
Redirects to login if not authenticated
🔹 Place Details
Displays detailed info about a selected place
Fetches data using place ID
Shows reviews
Allows adding review (if logged in)
🔹 Add Review
Form to submit a review
Only avaliable for authenticated users
Redirects unauthorized users
CORS(app)

# 🔧 Technologies Used

HTML5
CSS3
JavaScript (ES6)
Fetch API
JWT (JSON Web Token)
Cookies

# 📚 References

MDN Web Docs (HTML, CSS, JS)
Fetch API Documentation
JWT Authentication
Flask CORS Documentation