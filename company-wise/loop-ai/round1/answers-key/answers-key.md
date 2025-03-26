# Loop AI Interview Experience

### Round 1 : JS, React Fundamentals + React Coding Question

1. Brief introduction    

2. JS Fundamentals
    1. What do you know about promises in JavaScript? 

    Answer : A promise is a Javascript object representing the eventual completion or failure of an asynchronous operation.

        - Follow ups
            - Before promises. Do you know what was used?

            Answer : Callbacks were used before promises.
            
            A callback is a function passed to another function as an argument, and gets called when the async operation finishes.

            ```jsx
            function getData(url, callback) {
                xmlRequest = new XMLHttpRequest();

                xmlRequest.open('GET', 'utf-8', url);

                xmlRequest.onLoad(() => {
                    if(xmlRequest.status === 200) {
                        callback(xmlRequest.responseText, null);
                    }else {
                        callback(null, new Error("There was an issue with the request"));
                    }
                })

                xmlRequest.onError(() => {
                    callback(null, new Error("There was a network error"));
                })

                xmlRequest.send();
            }

            getData("https://www.google.com", (data, error) => {
                if(error) {
                    console.error(`Error: ${error}`)
                    return;
                }
                console.log(`Data : ${data}`)
            })
            ```

            Callbacks have major drawbacks like
                - Callback Hell : nested callbacks are tough to read and manage

                ```jsx
                <!-- With callbacks -->

                const api1 = "https://www.google.com";
                const api2 = "https://www.google.com/userCreds";
                const api3 = "https://www.google.com/userSearches";
                getData(api1, (data, error) => {
                    if(!error) {
                        getData(api2, (data, error) => {
                            if(!error) {
                                getData(api3, (error) => {
                                    if(!error) {
                                        <!-- And So On -->
                                    }
                                })
                            }
                        })
                    }
                })

                <!-- With promises -->

                fetch(api1)
                .then((response) => fetch(api2))
                .then(response => fetch(api3))
                .then((response) => {
                    <!-- handle data here -->
                })
                .catch((error) => {
                    <!-- handle error here -->
                })
                ```


                - Inversion of Control : We dont't have control over how callback would be handled inside the function
                - Error Handling : Handling errors is tricky in nested callbacks  

            - Have you ever used the Promise class?

            Answer : Yes, the Promise class provides several functionalities like 
            - new Promise(): the promise constructor to create a new promise
            - Promise.resolve: to create a resolved promise
            - Promise.reject: to create a rejected promise with an error
            - Promise.all: to wait for all promises to be resolved

            - What are the methods in the Promise class, which could also be used to handle promises? (Apart from .then(), and async await)

            Answer : Promise.all, Promise.allSettled, Promise.race

            - Explain Promise.all, Promise.allSettled, Promise.race

            Answer : 
            Promise.all : Waits for all promises to be fulfilled, rejects if any promise rejects
            Promise.allSettled : Waits for all promises to be fulfilled or rejected
            Promise.race : Waits for first promise to settle and settles accordingly

3. Tree shaking and have you ever implemented it?

Answer : A dead code elimination technique, which reduces bundle size, leading to faster load times and increased performance. Webpack bundler does this, taking advantage of static import/export statements.

4. Abort Controller and have you ever used it?

Answer : 

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
        Answer : '53' (String before + forces string coercion)
        2. ‘5’ - 2
        Answer : 3
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
    
