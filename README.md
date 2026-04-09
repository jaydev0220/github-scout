# GitHub Scout

This is the homework 1 from Frontend Development Course (114-2), a Vue 3 project created with AI tools.

## QA with AI

1.  Which line of code is responsible for 'remembering' the name I typed?

    > Line 4 (@src/App.vue). This creates a Vue "box" (ref) that automatically updates whenever you type in the input. The magic is in the `<input v-model="username">` which connects the input to this box — so they always stay in sync.

2.  What are those `v-if` attributes in elements?

    > `v-if` is a Vue tool that means "show this ONLY if..."<br>
    > Plain meaning:
    >
    > - `v-if="error"` → Show the error message only when there's an error
    > - `v-if="avatarUrl"` → Show the photo only when we have a photo URL

3.  How did you fix the centering problem? What was the issue?

    > The issue was in `src/assets/main.css`:<br>
    >
    > ```css
    > @media (min-width: 1024px) {
    > 	#app {
    > 		display: grid;
    > 		grid-template-columns: 1fr 1fr; /* This forced 2 columns */
    > 	}
    > }
    > ```
    >
    > **Why it broke centering:**<br>
    > The `grid-template-columns`: `1fr 1fr` split the content into two equal columns side-by-side. Since the app only has one column of content (input, button, image), it looked off-center because Vue's default template expects that grid.

4.  How did you move avatar below input?
    > 1. HTML Order:
    >
    >    ```html
    >    <input />
    >    <button />
    >    <img class="avatar" />
    >    <p class="error" />
    >    ```
    >
    > 2. CSS for input + button side-by-side:
    >
    >    ```css
    >    input {
    >    	margin-right: 8px; /* Space between input and button */
    >    }
    >    ```
    >
    > 3. CSS for avatar below:
    >
    >    ```css
    >    .avatar {
    >    	display: block; /* Forces onto new line */
    >    	margin: 1rem auto 0; /* Centers horizontally */
    >    }
    >    ```
