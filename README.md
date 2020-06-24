# PICTURE QUIZ

---

Who's ready to take a quiz?

![](https://media.giphy.com/media/uFmMNcXaDNrMCzjCMq/giphy.gif)

We all have taken online [quizzes like this](https://www.sporcle.com/games/g/world) when we are bored. Today we are going to build out our own quiz!

## GOAL

---

Today's quiz is going to respond to what the user types. The quiz is setup to name all the characters in Stranger Things. If the user names a correct character, then the screen updates with the picture of that character.

![](https://media.giphy.com/media/MYyJlxHOplSfcRaill/giphy.gif)

## INPUT EVENT LISTENERS

---

Click events are cool, but they aren't the event that triggered cool stuff in the example that launched this lesson.

There are two types of event listeners you might want to use that are more specific to the `<input>` Element/Node.

- **"change"** fires every time the user presses enter/return while typing in the input field.
- **"input"** fires ever time the user presses any key while typing in the input field.

```javascript
// Example of the change event listener

var textbox = document.querySelector("#ID OF THE TEXTBOX");
textbox.addEventListener("change", function(event) {
  console.log("You Changed!");
});

// Example of the input event listener
textbox.addEventListener("input", function(event) {
  console.log("Key pressed!");
});
```

## `.value` PROPERTY

The last, and perhaps most important piece of this code is the `.value` property, which tells you what's currently written inside a text box. You have had some exposure to this, but as a refresher:

```javascript
var textbox = document.querySelector("#ID OF THE TEXTBOX");

textbox.addEventListener("input", function(event) {
  console.log("Key pressed!");
  //.value will give you the content INSIDE the textbox
  console.log(textbox.value);
});
```

The console will log two statements every time the `input` field is updated. It will first log "key pressed" and then it will log whatever the value of the textbox is.

## TASKS

---

For today's lab you should do the following:

1. Using `document.querySelector` select for the input field. Store this information in a variable. 
2. Place an event listener on the input filed. Log to the console a message everytime a user updates the input field.
3. Store the `#pictureBox` portion of the DOM in a variable using `document.querySelector`.
4. Update the `#pictureBox` using conditionals and `innerHTML`. Start by getting the pictureBox to log something like "You chose Eleven!" if the user picks the correct person.
5. That's great, but it's pretty bland because it can only add one statement and never more. We can use the `+=` operator with `innerHTML` to log multiple HTML elements. An example could be:
```javascript
textbox.addEventListener("input", function(event) {
  if (textbox.value == "Eleven"){
    console.log("YOU GOT ELEVEN!")
    // This will update the textbox EVERYTIME you type in the value of "Eleven"
    pictureBox.innerHTML += `<h1>YOU GOT ELEVEN!</h1>`
  } else {
    console.log("No match...")
  }
})
```
6. Last but not least, the original version didn't actually use text at all. You'll want to add a full image tag instead. You can find all the images in the assets folder. An example of this would look like:
```javascript
textbox.addEventListener("input", function(event) {
  if (textbox.value == "Eleven"){
    console.log("YOU GOT ELEVEN!")
    pictureBox.innerHTML += `<img src="https://cdn.glitch.com/01b27d37-a07e-4e2e-8caf-659256274937%2FScreen%20Shot%202019-08-08%20at%208.39.11%20AM.png?v=1565269664594"/>`
  } else {
    console.log("No match...")
  }
})
```
7. There are seven more characters to go. Code out your conditional so that each character appears when their name is input into the `input` field.
8. Declare a function called `checkCorrect()` and place **ALL** of this inside the function. Then call this function (and only this function) inside the event listener.
9. Print a message to the `div` with an id of `#message` when the user has guessed all the correct characters.

## STRETCH CHALLENGES
---
- Auto-erase answers - When a user types in their guess and gets it right, the final version of the app instantly recognizes the correct answer and erases the text to let them make their next guess, but our current version requires the user to erase everything one character at a time.  
- Handle case-sensitivity - A user should probably get credit for "Eleven" or "eleven" or "ELEVEN". Find a way to make it work no matter what.  
- Eliminate duplicates - right now, each right answer can be entered multiple times to get the same image multiple times. That's fun, but it may not be what you wanted to happen.  
-Keep Score - Show the user how many correct answers they've gotten, as well as how many are possible to get. Give them some form of congratulatory message when they succeed in guessing everything.
- Add a timer - Using some new JavaScript methods (you'll likely need `setTimeout()` or `setInterval()` and want to consult some documentation on how those things work), see if you can create a countdown clock on the page somewhere that shows how much time they have left.  

