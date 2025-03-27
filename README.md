# Dutch-to-English

This is a simple web app that lets you input Dutch text and view it with **hover-based English translations**. When you move your mouse over a word, a translation (if available) will appear.

## Features

- Add your own Dutch text
- Hover over words to see possible English translations
- Uses the FreeDict Dutch-English dictionary

## Setup

### Requirements

- [Node.js](https://nodejs.org/)
- [Redis](https://redis.io/)

### Install & Run

1. **Clone the repo**:
   ```bash
   git clone https://github.com/andrijeski/Dutch-to-English.git
   cd Dutch-to-English
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Make sure Redis is running**  
   (Use `redis-server` or your OS's Redis service)

4. **Configure the server**  
   Edit `config/default.json` if needed:
   ```json
   {
     "server-http": {
       "host": "127.0.0.1",
       "port": 9988
     },
     "redis": {
       "host": "127.0.0.1",
       "port": 6379
     }
   }
   ```

5. **Start the app**:
   ```bash
   node app.js
   ```

6. **Open in your browser**:  
   [http://localhost:9988](http://localhost:9988)

## Updating the Dictionary

You can download the latest Dutch-English dictionary from [freedict.org/downloads](https://freedict.org/downloads/), extract it, and place it in the `Data/` directory.

To clear the Redis cache (after updating the dictionary):

```bash
redis-cli FLUSHALL
```
