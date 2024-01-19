
URL Shortening Service Documentation
Overview
This documentation provides information about the URL shortening service implemented in this project. The service allows users to generate short URLs for their long URLs and retrieve analytics for a given short URL.

Table of Contents
Endpoints
Generate Short URL
Get Analytics
Request and Response Examples
Generate Short URL
Get Analytics
Endpoints
Generate Short URL
URL: POST /
Description: Generates a new short URL for the provided long URL.
Request Body:
url (string, required): The long URL to be shortened.
Response:
id (string): The generated short ID.
Get Analytics
URL: GET /analytics/:shortId
Description: Retrieves analytics for a given short URL.
Parameters:
shortId (string, required): The short ID generated for the URL.
Response:
totalClicks (number): The total number of clicks on the short URL.
analytics (array of objects): Array containing visit history with timestamps.
Request and Response Examples
Generate Short URL Example
Request
json
Copy code
POST / HTTP/1.1
Content-Type: application/json

{
  "url": "https://www.example.com/long-url"
}
Response
json
Copy code
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": "abc123"
}
Get Analytics Example
Request
json
Copy code
GET /analytics/abc123 HTTP/1.1
Response
json
Copy code
HTTP/1.1 200 OK
Content-Type: application/json

{
  "totalClicks": 5,
  "analytics": [
    {
      "timestamp": 1642650788000
    },
    {
      "timestamp": 1642650801000
    },
    // ... more timestamps
  ]
}
This documentation provides a brief overview of the available endpoints, their descriptions, and examples of request and response structures. For more detailed information, refer to the code implementation in the respective files: controllers/url.js, models/url.js, and routes/url.js.





