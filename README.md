# xss-attack
experiments on xss attacks

## Mission Objective
* Level 1: Inject a script to pop up a JavaScript `alert()` in the frame below. 
* Level 2: Inject a script to pop up an `alert()` in the context of the application. 
* Level 3: Inject a script to pop up a JavaScript `alert()` in the app. Since you can't enter your payload anywhere in the application, you will have to manually edit the address in the URL bar below.
* Level 4: Inject a script to pop up a JavaScript `alert()` in the application.
* Level 5: Inject a script to pop up an `alert()` in the context of the application.
* Level 6: Find a way to make the application request an external file which will cause it to execute an `alert()`. 

## Level 1 Hello, world of XSS
1. To see the source of the application you can right-click on the frame and choose View Frame Source from the context menu or use your browser's developer tools to inspect network traffic.
2. What happens when you enter a presentational tag such as `<h1>`?
3. Alright, one last hint: `<script> ... alert ...`

## Level 2 Persistence is key
1. Note that the "welcome" post contains HTML, which indicates that the template doesn't escape the contents of status messages.
2. Entering a `<script>` tag on this level will not work. Try an element with a JavaScript attribute instead.
3. This level is sponsored by the letters i, m and g and the attribute onerror.

## Level 3 That sinking feeling...
1. To locate the cause of the bug, review the JavaScript to see where it handles user-supplied input.
2. Data in the window.location object can be influenced by an attacker.
3. When you've identified the injection point, think about what you need to do to sneak in a new HTML element.
4. As before, using `<script> ...` as a payload won't work because the browser won't execute scripts added after the page has loaded.

## Level 4 Context matters
1. Take a look at how the startTimer function is called.
2. When browsers parse tag attributes, they HTML-decode their values first. `<foo bar='z'>` is the same as `<foo bar='&#x7a;'`
3. Try entering a single quote (`'`) and watch the error console.
  
## Level 5 Breaking protocol
1. The title of this level is a hint.
2. It is useful look at the source of the signup frame and see how the URL parameter is used.
3. If you want to make clicking a link execute Javascript (without using the onclick handler), how can you do it?
4. If you're really stuck, take a look at this IETF draft (https://tools.ietf.org/html/draft-hoehrmann-javascript-scheme-00)

## Level 6 Follow the 🐇
1. See how the value of the location fragment (after `#`) influences the URL of the loaded script.
2. Is the security check on the gadget URL really foolproof?
3. Sometimes when I'm frustrated, I feel like screaming...
4. If you can't easily host your own evil JS file, see if https://google.com/jsapi?callback=foo will help you here.
