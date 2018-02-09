# xss-attack
experiments on xss attacks

## Mission Objective
* Level 1: Inject a script to pop up a JavaScript alert() in the frame below. 
* Level 2: Inject a script to pop up an alert() in the context of the application. 
* Level 3: Inject a script to pop up a JavaScript alert() in the app. Since you can't enter your payload anywhere in the application, you will have to manually edit the address in the URL bar below.
* Level 4: 

## Level 3
1. To locate the cause of the bug, review the JavaScript to see where it handles user-supplied input.
2. Data in the window.location object can be influenced by an attacker.
3. When you've identified the injection point, think about what you need to do to sneak in a new HTML element.
4. As before, using <script> ... as a payload won't work because the browser won't execute scripts added after the page has loaded.

## Level 4
