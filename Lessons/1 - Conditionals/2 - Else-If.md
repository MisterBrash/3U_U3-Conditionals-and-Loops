# Unit 3 - Conditionals and Loops

## 3.2 - Else-If

##### ICS3 - Mr. Brash 🐿️

<table>
<tr>
<th>
3.2 - In this Lesson:
</th>
<th>
Unit 3 - Conditionals & Loops
</th>
</tr>
<tr>
<td td valign="top" style="height: 100px;padding-right:50px">
<ul>
<li><a href="#lesson">Else-If Syntax</a></li>
<li><a href="#examples">Examples</a></li>

<li><a href="#practice-time">Practice Time!</a></li>
<ul>
<li><a href="#part-1">Part 1</a></li>
<li><a href="#part-2---and-and-or">Part 2</a></li>
<li><a href="#part-3">Part 3</a></li>
<li><a href="#part-4">Part 4</a></li>
</ul>
</ul>
</td>
<td td valign="top" style="height: 100px;padding-right:50px">
<ul>
<li><a href="../../README.md">README</a></li>
<li><a href="./1 - If.md">3.1 - If</a></li>
<li><a href="./2 - Else-If.md">3.2 - Else-If</a></li>
<li><a href="./3 - Else.md">3.3 - Else</a></li>
<li><a href="../2 - Loops/4 - While.md">3.4 - While</a></li>
<li><a href="../2 - Loops/5 - Do-While.md">3.5 - Do...While</a></li>
<li><a href="../2 - Loops/6 - For.md">3.6 - For</a></li>
<ul>

</td>


</tr>
</table>

---

### Lesson:

The `if-statement` allows us to make decisions with code:
```JS
if (age >= 60) {
    console.log("You old!")
}
```

**But what if we needed to make *several* decisions based on fairly complex conditions?**

For example - the user selects a colour based on a number:
```JS
let selection = prompt("Enter 1 for red, 2 for blue, 3 for green, 4 for purple")

if (selection == 1) {
    // Do something
}

if (selection == 2) {
    // Do something else
}

if (selection == 3) {
    // Do something else
}

if (selection == 4) {
    // Do something else
}
```

In the above example, the code is going to check the variable `selection` FOUR times, even if the user entered "1" or a number not in the list, like "8". *That's a lot of wasted checking.*


<div style="text-align:center;"><p>The <code>if-statement</code> has another optional piece that will help with this scenario.</p><img src="../images/else-if.png" width="500px"></div>

The `else if` block will *only* be checked if the condition above it was `false`.<br>Let's retry our colour selection example:
```JS
let selection = prompt("Enter 1 for red, 2 for blue, 3 for green, 4 for purple")

if (selection == 1) {
    // Do something for red
} else if (selection == 2) {
    // Do something else for blue
} else if (selection == 3) {
    // Do something else for green
} else if (selection == 4) {
    // Do something else for purple
} 
```
In the code above, if the user enters "2", the code will check if it's equal to 1 (it's not), then check if it's equal to 2 (it is) and it will **NOT** check any of the other conditions - it will run the block of code for `== 2` and then _skip over the rest of the else-if statements_.

**Note:** You can have as many `else if` statements as you need but only *one* `if` at the beginning.

### Final Notes:

- To get the **_length_ of a String**, we can use `.length`<br>For Example:<br>
  ```JS
  let name = "Mr. Squirrel"
  console.log("Your name is", name.length, "characters long.")
  ```
- The internet is full of [tutorials](https://javascript.info/ifelse), [more tutorials](https://www.w3schools.com/js/js_if_else.asp), and [examples](https://www.google.com/search?q=if+else+statement+example) about the if-else statement since it is one of the very first constructs people learn in programming.


## Practice Time!

### Part 1 - 


Create the function `menu()` that does the following:

1. Ask the user for their name (using `prompt()`) and store it in `user_name`.

2. Now we're going to display a menu. Menus are a good example of using if-statements to control the flow of a program. Copy and paste the following to your code to display a menu:  
    ```JS
    // Setup the menu
    let message = `Hi ${user_name}. Please make a selection:
    1 - Play
    2 - Options
    3 - DLC
    4 - Check for Updates
    5 - Exit
    `
    // Prompt with the menu
    let selection = Number(prompt(msg));
    ```

    Whatever number they select will be stored in `selection`.

    Based on what the user selects, use an if-statement and else-if statements to output (console.log) the following:

    | Value | Output |
    |---|---|
    |1|"Let's play!"|
    |2|"You selected Options."|
    |3|"No new DLC at this time."|
    |4|"Everything is up to date."|
    |5|"Bye!"|

3. If the user selects `1 - Play`, we should then ask them a difficulty level of `1 - Easy`, `2 - Medium`, or `3 - Hard`. After you print "Let's play!" to the console, prompt the user for their selection of difficulty.  
Depending on what they select, output the following:
    | Value | Output |
    |---|---|
    |1|"You selected the easy route."|
    |2|"Most people select medium."|
    |3|"I see you like a challenge!"|  
  
    > 🤔 Just a thought... what if they don't enter one of those choices?  
     🤷‍♂️ I guess that's for another lesson.
  
<br>

---

### Part 2 - AND and OR

As mentioned in the previous lesson, you can combine _conditions_ with logical "AND" or "OR" operators. For example, to check if a number is between 5 and 10:
```JS
if ((x >= 5) && (x <= 10)) {
  // Do something
}
```

In that example, it is checking if the value is greater than or equal to 5 **and** less than or equal to 10. The symbol for **and** is double ampersands, `&&`. The symbol for **or** is double pipes, `||` (the key is above the enter key on your keyboard).

- Ask the user to enter an hour between 0-23 ([military time](https://en.wikipedia.org/wiki/24-hour_clock)). Just the hour, no minutes. Depending on their entry, output "Good morning!" (hour is 0-11), "Good afternoon!" (hour is 12-17), or "Good evening!" (hour is 18-23). If the hour is any other value, output "Invalid hour!".

### Here's another optional challenge:

- `Math.random()` creates a random number between 0 and 1. For example, it might give you 0.42564821 or some nonsense like that.  Multiplying by 10 will give us a single-digit value above zero:  4.2564821<br>
We can chop the decimals off by using [Math.floor( )](https://www.w3schools.com/jsref/jsref_floor.asp) or [Math.trunc( )](https://www.w3schools.com/jsref/jsref_trunc.asp):
```JS
let random_number = Math.random() * 10;     // Get a single-digit value (with decimals)
random_number = Math.floor(random_number);  // Chop off the decimals

// Optionally, parseInt will also work:
random_number = parseInt(random_number);
```
Generate a random single-digit value and give output based on the following:
- If the value is zero, say so
- If the value is `even`, say so
- If the value is divisible by 2 _AND_ 3, say so
- If the value is **_prime_**, say so

Keep in mind, those are not ELSE-IF situations.

<br><br>

🐿️

