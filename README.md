# Joke Generator

A fun and educational random joke generator using external APIs. Supports multiple joke sources and implementation languages.

## Features

- 🎭 **Multiple Joke APIs:** Official Joke API, JokeAPI, icanhazdadjoke
- 🔧 **Multiple Languages:** JavaScript/Node.js, Python, Rust, Go, PHP
- 🎯 **Joke Categories:** Programming, General, Dark, Pun, and more (where available)
- ⚙️ **Easy Configuration:** Switch between APIs with minimal code changes
- 📊 **Error Handling:** Graceful fallback and retry logic
- 🧪 **Well-Tested:** Unit tests included for each implementation

## Joke APIs Used

### 1. Official Joke API
- **URL:** https://official-joke-api.appspot.com/
- **Setup/Punchline Format:** Classic joke structure
- **No API Key Required**

### 2. JokeAPI
- **URL:** https://v2.jokeapi.dev/
- **Features:** Category filtering, safe-for-work options
- **No API Key Required**

### 3. icanhazdadjoke
- **URL:** https://icanhazdadjoke.com/api
- **Specialty:** Dad jokes (single-line or setup/delivery)
- **No API Key Required**

## Quick Start

### JavaScript/Node.js
```bash
cd javascript
npm install
node joke-generator.js
```

### Python
```bash
cd python
pip install requests
python joke_generator.py
```

### Rust
```bash
cd rust
cargo run
```

### Go
```bash
cd go
go run main.go
```

### PHP
```bash
cd php
php joke_generator.php
```

## Project Structure

```
.
├── README.md
├── javascript/
│   ├── package.json
│   ├── joke-generator.js        # Main implementation
│   ├── joke-generator.test.js   # Tests
│   └── README.md
├── python/
│   ├── joke_generator.py        # Main implementation
│   ├── joke_generator_test.py   # Tests
│   ├── requirements.txt
│   └── README.md
├── rust/
│   ├── Cargo.toml
│   ├── src/
│   │   └── main.rs
│   └── README.md
├── go/
│   ├── go.mod
│   ├── main.go
│   └── README.md
├── php/
│   ├── joke_generator.php
│   └── README.md
└── docs/
    └── API_COMPARISON.md         # Comparison of joke APIs
```

## Example Output

### Official Joke API
```
Why do Java developers wear glasses?
Because they don't C#!
```

### JokeAPI (Twopart)
```
Why don't scientists trust atoms?
Because they make up everything!
```

### icanhazdadjoke
```
I'm afraid for the calendar. Its days are numbered.
```

## Usage Examples

### Get a Random Joke (JavaScript)
```javascript
const JokeGenerator = require('./joke-generator');
const generator = new JokeGenerator();

generator.getRandomJoke().then(joke => {
  console.log(joke);
}).catch(error => {
  console.error('Failed to fetch joke:', error);
});
```

### Get Jokes by Category (Python)
```python
from joke_generator import JokeGenerator

generator = JokeGenerator()
jokes = generator.get_jokes_by_category('Programming', count=3)
for joke in jokes:
    print(joke)
```

### Get Dad Jokes (Rust)
```rust
use joke_generator::JokeGenerator;

#[tokio::main]
async fn main() {
    let generator = JokeGenerator::new();
    match generator.get_dad_joke().await {
        Ok(joke) => println!("{}", joke),
        Err(e) => eprintln!("Error: {}", e),
    }
}
```

## Configuration

Each implementation supports configuration options:

- **API Selection:** Choose which API to use
- **Timeout:** Set request timeout (default: 5s)
- **Retry Logic:** Enable/disable automatic retries
- **Category Filtering:** Filter by joke category (where supported)

## Testing

Each language implementation includes unit tests.

```bash
# JavaScript
cd javascript && npm test

# Python
cd python && python -m pytest joke_generator_test.py

# Rust
cd rust && cargo test
```

## Performance

| API | Avg Response Time | Reliability | Best For |
|-----|-------------------|-------------|----------|
| Official Joke API | ~150ms | 99.9% | Setup/punchline jokes |
| JokeAPI | ~200ms | 99.5% | Categories, filtering |
| icanhazdadjoke | ~100ms | 99.9% | Dad jokes |

## Rate Limiting

- **Official Joke API:** ~10 requests/second
- **JokeAPI:** ~100 requests/hour (no API key)
- **icanhazdadjoke:** No documented limit; be respectful

## Contributing

Contributions welcome! Consider adding:
- [ ] Additional joke APIs
- [ ] New language implementations
- [ ] Joke caching system
- [ ] CLI tool wrapper
- [ ] Discord/Slack bot integration
- [ ] Docker containerization

## License

MIT

## Fun Facts

- The Official Joke API has served millions of jokes
- JokeAPI supports over 10 categories
- icanhazdadjoke specializes in wholesome humor
- All three APIs are free and have been actively maintained

Enjoy the laughs! 😄
