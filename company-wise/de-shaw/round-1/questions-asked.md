# D.E. Shaw Interview Experience

## Round 1

1. Brief Introduction
2. Why use GraphQL?
3. How does Context API improve performance? (From resume)
    - Follow ups
        - Why not use Redux over context api?
        - Would redux be helpful in any case?
4. Print output of following
    
    ```jsx
    async function async1() {
      console.log("async1 start");
      await async2().then((r)=> console.log("hey",r)).then((r)=> console.log("hey2",r));
      console.log("async1 end");
    }
    
    async function async2() {
      console.log("async2");
    }
    
    console.log("script start");
    
    setTimeout(function () {
      console.log("setTimeout");
    }, 0);
    
    await async1();
    
    new Promise(function (resolve) {
      console.log("promise1");
      resolve();
    }).then(function () {
      console.log("hey3");
    });
    
    console.log("script end");
    ```
    
5. Print output of following
    
    ```jsx
    let count = 0;
    (function immediate() {
      if (count === 0) {
        var count = 1;
        console.log(count, "1"); // What is logged?
      }
      console.log(count, "2"); // What is logged?
    })();
    console.log(count, "3") // What is logged?
    ```
    
6. Print output of following
    
    ```jsx
    var count = 0;
    (function immediate() {
      if (count === 0) {
        let count = 1;
        console.log(count , "1"); // What is logged?
      }
      console.log(count, "2"); // What is logged?
    })();
    ```
    
7. Given x, and y, how can I make all properties of y available to x.
    
    ```jsx
    x ={a: 3, b:4}
    y ={c:6, d:7}
    
    // x.c should be accessible and equal to 6.
    ```
    
8. Design a Real-time Market Data Component with below features
    1. live updating list of market prices for selected financial instruments (20,000 stocks ticking real time)
    2. Include features like Realtime sorting, filtering, and searching 
    3. Ensure updates are reflected in the UI within milliseconds of data change without crashing the UI