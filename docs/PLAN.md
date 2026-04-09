# GitHub User Search App - Plan

## What the app does
User types a GitHub username → clicks button → sees that user's profile photo appear on screen.

---

## Step-by-Step Process (Explained Simply)

| Step | What Happens | What's Really Going On |
|------|--------------|----------------------|
| 1 | You type a name in the box | Browser saves your typing in a Vue "box" (ref) |
| 2 | You click the button | Browser fires an event that triggers the search |
| 3 | Your browser sends a message to GitHub | Vue calls GitHub's API with the username |
| 4 | GitHub searches for that person | API looks up user in GitHub's database |
| 5 | GitHub sends back the user's info | API returns JSON with avatar_url |
| 6 | Your app receives the response | Vue stores the photo URL in a "box" |
| 7 | The photo shows on screen | Vue displays the image using the URL |

---

## Technical Implementation Steps

1. **Create text input** - Vue `<input>` bound to a ref for username
2. **Create button** - Vue `@click` that calls a search function
3. **Create API call** - Use `fetch()` to call `https://api.github.com/users/{username}`
4. **Handle the response** - Store `avatar_url` from API in a ref
5. **Display the image** - Use Vue `<img :src="avatarUrl">` to show photo
6. **Handle errors** - Show message if user not found
7. **Fix centering** - Remove 2-column grid layout from main.css
8. **Move avatar below input** - Restructure template to show avatar between input and button

---

## Completed Steps

- Step 1-7: Implemented and fixed

---

## Step 8: Move Avatar Below Username Input

**Current Layout:**
```
[Input] [Button]
[Error message]
[Avatar]
```

**New Layout:**
```
[Input] [Button]
[Avatar]
[Error message]
```

**Implementation:**
- Reorder elements in the template so `<img>` appears after `<input>`
- Adjust CSS spacing/margins accordingly
- Keep functionality the same

---

## Future Improvements (Phase 2)

- Add user name and bio display below avatar
- Add loading spinner
- Style the form nicely (input + button inline)
- Add dark mode support
- Handle rate limiting from GitHub API
