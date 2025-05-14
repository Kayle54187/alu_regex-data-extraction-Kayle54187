# Regex Data Extraction Project

A web form with 8 regex-powered validations for:

- Email addresses
- URLs
- Phone numbers
- Credit cards
- Time formats (12h/24h)
- HTML tags
- Hashtags
- Currency amounts

## Setup

1. Clone the repo:
   ```bash
   git clone https://github.com/your-username/alu_regex-data-extraction-yourusername.git
   ```
2. Open `index.html` in a browser.

## 🧪 Test Cases

Full test cases available in [test_cases.txt](/tests/test_cases.txt). Examples:
| Validation | Valid Example | Invalid Example |
|-------------|---------------------|-----------------------|
| Email | `user@domain.com` | `user..name@domain` |
| Currency | `$1,234.56` | `$1.234` |
| Time | `14:30` | `25:00` |

## 🔍 Regex Patterns

```javascript
// Email: Prevent consecutive dots
/^(?!.*\.\.)[\w.%+-]+@[\w.-]+\.[a-zA-Z]{2,}$/

// Credit Card: Enforce consistent separators
/^\d{4}([ -]?)\d{4}\1\d{4}\1\d{4}$/

// Hashtags: Allow accents and numbers
/^#[\w\u00C0-\u00FF]+(?:\s#[\w\u00C0-\u00FF]+)*$/
```

## 🛠 Edge Case Handling

- **Phone Numbers**: Supports `()`, `.`, `-`, and space separators
- **HTML Tags**: Rejects closing tags and unclosed brackets
- **Currency**: Requires proper comma placement (e.g., `1,000` not `1,00`)

## 📜 License

MIT License. See [LICENSE](LICENSE) for details.
