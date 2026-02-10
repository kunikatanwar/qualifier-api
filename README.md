Qualifier API

This is a Node.js API project that provides multiple features including Fibonacci series, Prime number filtering, HCF, LCM, and an AI-powered single-word answer using Google Gemini API.

Features

Health Check

Endpoint: GET /health

Returns your email and API health status.

Fibonacci Series

Endpoint: POST /bfhl

Request Body:

{
  "fibonacci": 10
}


Returns the first n Fibonacci numbers.

Prime Numbers

Endpoint: POST /bfhl

Request Body:

{
  "prime": [1,2,3,4,5,6,7]
}


Returns only the prime numbers from the array.

HCF (Highest Common Factor)

Endpoint: POST /bfhl

Request Body:

{
  "hcf": [12, 18, 24]
}


Returns the HCF of the array numbers.

LCM (Lowest Common Multiple)

Endpoint: POST /bfhl

Request Body:

{
  "lcm": [4, 5, 10]
}


Returns the LCM of the array numbers.

AI Single-Word Answer

Endpoint: POST /bfhl

Request Body:

{
  "AI": "Capital of Maharashtra?"
}


Returns a single-word AI answer using Google Gemini API.

If API fails or quota is exceeded, fallback answers are provided (e.g., Mumbai for Maharashtra).

Installation

Clone the repository:

git clone https://github.com/kunikatanwar/qualifier-api.git
cd qualifier-api


Install dependencies:

npm install


Create a .env file in the root directory with your Gemini API key:

GEMINI_API_KEY=your_api_key_here

Usage

Start the server:

node server.js


Test endpoints using Thunder Client or Postman:

Health: GET http://localhost:3000/health

API: POST http://localhost:3000/bfhl with request body depending on feature.

Example Requests & Responses

Fibonacci

POST /bfhl
{
  "fibonacci": 5
}

Response:
{
  "is_success": true,
  "official_email": "kunika0471.be23@chitkara.edu.in",
  "data": [0, 1, 1, 2, 3]
}


AI Question

POST /bfhl
{
  "AI": "Capital of Maharashtra?"
}

Response:
{
  "is_success": true,
  "official_email": "kunika0471.be23@chitkara.edu.in",
  "data": "Mumbai"
}

Notes

Only one operation per request is allowed. Sending multiple keys will result in an error.

AI feature uses Google Gemini API, ensure your API key is valid and has sufficient quota.

Fallback logic is implemented for AI in case of API errors or quota limits.

Author

Kunika Tanwar
Email: kunika0471.be23@chitkara.edu.in
