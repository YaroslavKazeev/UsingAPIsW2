# Prep exercise - Cat walk with async/await

In the previous week we changed the cat walk to an implementation using `Promise`s. Let's now use the new `async/await` syntax to simplify it a little more. Have a look at the `index.js` to see what to do.

The `dance` and `walk` functions are identical to last week, but our `catWalk` function can now be implemented using a standard `while` loop. Try to implement that and look at the following questions.

## Things to think about

- Do you feel this version is easier to read than the version you made in the previous week?

The async-await syntax has no advantages compared to .then syntax with resolving promises, as it is more complicated for creating promises.

- Is this version more efficient or not or is there no difference?

There is no difference.

- Async/await makes the code wait until the Promise is resolved. Does this then also block any other functions from running? Why or why not?

The async/await code behavior is no different from the Promise.then() one. It also prioritizes the microtask queue over the task queue.
