# Loop AI Interview Experience

### Round 1 : JS, React Fundamentals + React Coding Question

1. Brief introduction
2. JS Fundamentals
    1. What do you know about promises in JavaScript? 
        - Follow ups
            - Before promises. Do you know what was used?
            - Have you ever used the Promise class?
            - What are the methods in the Promise class, which could also be used to handle promises? (Apart from .then(), and async await)
            - Explain Promise.all, Promise.allSettled, Promise.race
3. Tree shaking and have you ever implemented it?
4. Abort Controller and have you ever used it?
5. Event Delegation and Event Bubbling
6. What are the optimisation techniques we can use for a react application which is not performing well?
    - Follow ups
        - Server side rendering
            - Have you implemented server side rendering?
            - What are the possible edge cases you have to keep in mind when implementing SSR?
            - Lets say you have implemented SSR in a blog page. Then you add couple of blogs directly to the database. These blogs won’t reflect immediately in your SSR result. What measures can you take to ensure you’re always getting the up to date state in your SSR result?
                - Interviewer told its called incremental site rendering in Next.JS
7. JS Quiz questions
    1. Whats the output of following
        1. ‘5’ + 3
        2. ‘5’ - 2
        3. true + false
        4. typeof null
        5. null == undefined
        6. null === undefined
        7. [] == false
        8. 0.1 + 0.2 === 0.3
        9. !!"false" 
        10. !!0
        11. 1 < 2 < 3
8. React Coding Question
    
    You are building a React application where users can search for items in a database. To optimize performance, you need to debounce the search input so that API calls are made only after the user has stopped typing for a short duration.
    
    **Write a custom React hook called useDebounce that:**
    Accepts a value and a delay in milliseconds as parameters.
    Returns the debounced value after the specified delay.
    Updates the debounced value only when the input value remains unchanged for the given delay.
    
    Example usage:
    
    ```jsx
    const debouncedSearch = useDebounce(searchQuery,1000);
    ```
    
