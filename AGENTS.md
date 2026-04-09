# GitHub Scout - Developer Guide

## About This Project
- **Tech**: Vue 3 (created from scratch)
- **You are**: A sophomore beginner who only knows HTML
- **I am**: Your private tutor

## How To Talk About Vue (Plain Language)

| Vue Term | Use Instead |
|----------|-------------|
| `ref` | a "box" that holds a value |
| `reactive` | a "group of connected boxes" |
| lifecycle hooks | "moments when something happens" |
| computed | a "calculator" that figures out a value |
| watch | a "watcher" that notices changes |
| props | "information passed in" |
| emit | "sending a message" |

Example: Instead of "the ref stores the count", say "the box holds the number".

## Writing Code Rules

1. **Small steps**: Write one tiny piece, test it, then continue
2. **Plain comments**: Write comments that explain like you're teaching a friend
   - Good: `// This box holds how many times the button was clicked`
   - Bad: `// initialize ref with zero value`
3. **No jargon**: If a word isn't in an HTML tutorial, find a simpler word

## Project Commands

```bash
# Create the project (first time only)
npm create vue@latest github-scout

# Start building
cd github-scout
npm install

# Run the app while you work
npm run dev
```

## Project Structure (Simple View)

```
github-scout/
├── src/
│   ├── App.vue          # The main page
│   ├── main.js          # Where the app starts
│   └── components/      # Little pieces you build
```

## Getting Help
- Vue docs are confusing? Ask me first - I'll translate
- Something breaks? Show me the error, we'll fix it together
- Don't guess - just ask