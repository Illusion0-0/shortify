# Shortify - URL Shortener Service

Shortify is a URL shortener service implemented using Node.js, Express, and MongoDB. It allows you to shorten long URLs into short, more manageable links.

## Features

- Shorten long URLs into unique, shortened links.
- Redirect shortened links to the original long URLs.
- Track and display the visit history of shortened links.

## Requirements

- Node.js (version 12 or higher)
- MongoDB

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/Illusion0-0/shortify.git
   ```

2. Navigate to the project directory:

   ```bash
   cd shortify
   ```

3. Install the dependencies:

   ```bash
   npm install
   ```

4. Start the server:

   ```bash
   npm start
   ```

5. Access the application by visiting `http://localhost:8001` in your browser.

## Usage

1. On the homepage, enter a long URL that you want to shorten and click the "Shorten" button.

2. You will be redirected to a page that displays the shortened URL.

3. Copy the shortened URL and share it with others.

4. When someone accesses the shortened URL, they will be redirected to the original long URL.

5. To view the visit history of a shortened URL, append `+` to the end of the shortened URL. For example, `http://localhost:8001/abc+`.

## Database Schema

The MongoDB database contains a collection named `urls` with the following schema:

```javascript
const urlSchema = new mongoose.Schema(
  {
    shortId: {
      type: String,
      required: true,
      unique: true,
    },
    redirectURL: {
      type: String,
      required: true,
    },
    visitHistory: [{ timestamp: { type: Number } }],
  },
  { timestamps: true }
);
```

- `shortId`: The unique identifier for the shortened URL.
- `redirectURL`: The original long URL.
- `visitHistory`: An array of timestamps representing the visit history of the shortened URL.
