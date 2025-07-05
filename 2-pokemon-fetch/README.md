# Prep exercise - Error handling

Until this week the code you have been working on is mostly your own and is generally very static which means that if it works once it will most likely keep working in the same way. When interacting with external API's over the internet this goes out the window. You have no control over the data the API gives and although usually fine, the internet is always going to be unreliable. This means your code needs to be able to handle it when something goes wrong and inform the user.

In this exercise we'll focus on the fetching and error handling part of working with an API, which you can use to work with any other code where a possible problem can occur. The `index.js` gives you instructions on what to do, there is some code there already, but feel free to alter that if needed.

The expected behaviour is as follows:

- When you press the **Get Data** button with the **Use invalid URL** checkbox **unchecked** the data from the Pokemon API will be fetched and rendered as JSON on the page.
- When you press the button with the checkbox **checked** an HTTP error message will be rendered on the page.

## Things to think about

- If you look at the `index.html` you can see our error rendering is put into a regular `div` element, but our pokemon json is put into a `pre` element. Why is that?

The pre HTML tag allows to preserve the format of the text when displayed in the browser window. That is important because otherwise the content of JSON will be in one string and become difficult to read.

- The comments say to handle the error in the main function. What do you think the advantages are of doing it this way? What about if you would do the error handling in the `fetchJSON` function?

It is ok to have error handling right after the error occurs. The good practice is to rethrow the error and pass it for subsequent use in further .then/await chain, that will ensure that promises downstream of the error are not mistakenly resolved, leading to unpredictable outcomes.

- Some students ask us why not just put `try/catch` blocks around the main function and have that as the place to catch all errors. Why do you think we do not suggest doing this?

The main function should be tested before shipping to customers. There should not be any errors at that point, except the errors that emerge from using the Internet and APIs; that's why try/catch blocks should be only inside the asynchronous functions that use those external requests.
