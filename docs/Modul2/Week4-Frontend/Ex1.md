# Exercise 1: Frontend programming

Clone the start project from: [FrontEnd starter code](https://github.com/HartmannDemoCode/frontendEx1.git) and open the project in netbeans

## 1. Style with pure CSS

1. Open the file: cssex1.html
2. Link a new stylesheet to the html page.
3. Change the look of the content in div with id = top_menu. Make it a [horisontal menu: ](https://www.w3schools.com/css/css_navbar.asp)
4. Change the look of the content in div with id = left_menu. Make it a vertical navigation bar to the left side (under the top menu)
5. Change the look of the content in div with id = right_content. Make it sit to the right side of the left_menu. Give it an appropriate font-family, border and padding etc.

## 2. Style with bootstrap

1. Open the file: cssex2.html setup links to bootstrap CDN: [Look here](https://www.w3schools.com/bootstrap/bootstrap_get_started.asp).
2. Use bootstrap to get a top menu, a left menu and a zebra striped look on the table in the right side content div (Hint: use [Bootstrap grid](https://www.w3schools.com/bootstrap/bootstrap_grid_basic.asp) to get the left and right hand side)
3. Play around with different bootstrap tricks to prittyfy the content.

## 3. Javascript functionality

In this exercise we use the index.jsp file and the scripts/script.js file to make our solution. 

when you develop with javascript allways have your **browser console** window open to detect any **errors**!!

1. Look at the script.js file: see how the submit event handler is implemented. 
2. Extend it to also validate input from the other input fields (Use the regular expressions to check if the character pattern for the input is right.)
3. Implement the eventhandlers for the 8 of the 10 buttons in the right view pane
   1. consoleLog: Implement the eventhandler so you can write to the browser console: The time is `current time` (Hint get the time like this: ` Date();`
   2. When this button is clicked its color should change. (Hint use 'this' keyword to reference the element behind the event: `this.style.backgroundColor = 'red';`)
   3. Change color in TH: The exercise here is to target all the `<th>` tags by using `document.getElementByTagName`. This will return an array of all elements of type table header. In order to set `.style.color = 'pink'` on each of them. the collection must be looped over. (hint: use a normal for loop).
   4. Make an eventhandler to this button that can hide the logo if it is shown and show it if it is hidden. (Hint: select the surrounding div with id=logo. save the information about its innerHTML (in a variable outside the eventhandler function (only if the variable is empty)). Then if the innerHTML is empty give it the content of the variable - else give it an empty string)
   5. Remove the first row of buttons. Hint: use the surrounding div and set its innerHTML to an empty string;
   6. Look at the implementation of the 'sort by firstname' click event handler. Based on the code in this eventhandler now implement the eventhandler code for the 'sort by lastname' button
   7. In the same way now look at the implementation of 'filter on female' and implement the filter on male button.
   8. Finally implement the 'Sum account' event handler so that we get the sum of all the listed accounts.