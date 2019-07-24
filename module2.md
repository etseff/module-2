## The Basics


In this module, you’ll learn about the core technologies that you’ll be using to create store pages.

To complete this section of the training clone the repo locally. Check out a branch called `<your-name>-answers`. This will be the base branch that contains your work for training. Check out a new branch (call it whatever you want) and use a markdown plugin in the editor of your choice to fill in your answers. At the end of each day, or when you're finished with the module, create a pull request to merge into `<your-name>-answers` for your mentor to review.
Address any comments they leave before merging.

## HTML

1. What does the doctype tag do?
    ``` 
    It specifies to the browser that you wrote an HTMl file and what version
    ```
2. What information is usually contained in the head tag? Why might it not be a good idea to put script tags in the head?
    ``` 
    The head tag describes the preliminary information about the webpage (metadata).You shouldn't put script tags in the head because it won't load the rest of the webpage until the script files are loaded. 
    ```
3. Which of the following is not a use for meta tags (please explain your choice)? 

    a. Marking up information with schema that isn’t explicitly displayed on the page
    
    b. Controlling what is displayed for a web page’s search results
    
    c. Temporarily storing user input before a form is submitted
    
    d. Determining if all phone numbers on the page will become links that kick off phone calls for mobile users	
    ``` 
    c: Metadata is used to provide information about the webpage, not store new information
    ```
4. What is the tag that contains the visible contents of the HTML page?
    ```
    body
    ```
5. What is the difference between a div tag and a span tag? When would you favor a div over a span? When would you favor a span over a div?
    ```
    div is block-line (always starts on a new line). It should be used for big chunks of code.
    span is in-line (starts on same line). It should be used for small chunks of code.
    div inside a span won't work until you display: block the span
    ```
6. What are the action and method attributes of a form tag? What are the appropriate values for the method attribute and what is the effect of each when the form is submitted?
    ```
    action specifies where to send form data when a form is submitted. method specifies how to send form data. get is used to send as url variables, and post is used to send as an http post transaction. 
    ```
7. Suppose you had an HTTP server that accepts requests to create blog posts. What HTTP verb would you use to instruct the server to create a new post? Why?
    ```
    post, because it sends the data as an http post transaction
    ```
8. Suppose this endpoint expected a title, author, postType and body. How would you configure the form’s elements so that the values from your form matched the expected parameter names?
    ```
    <form action = "/something" method = "post">
        Title: <input type="text" name="title"><br>
        Author: <input type="text" name="author"><br>
        Post Type: <input type="text" name="postType"><br>
        Body: <input type="text" name="body"><br>
    </form>
    ```
9. When your form has a lot of checkboxes on it, how can you use the Label tag to make clicking those check boxes easier for the user? Why is this important for accessibility?
    ```
    <label for="box">Checkbox:</label>
    <input type="checkbox" id="box" name="box">
    
    This makes it easier for the user because the user can click on the checkbox or the label to check off the checkbox, giving the user greater clicking area. This is important for accessibility because it makes clicking the checkbox more simple for the user.
    ```
10. What types of controls can you build using the input tag?
    ```
    button, checkbox, color, date, datetime-local, email, file, hidden, image, month, number, password, radio, range, reset, search, submit, tel, tixt, time, url, week
    ```
11. When would you use a select tag? How might you improve the user’s experience when the number of options in list is enormous?
    ```
    The select tag creates a drop down list with options for the user. You can improve the user's experience when the number of options is enormous by using the optgroup tag. The optgroup tag can be used to group multiple options together. You could also use javascript to create a search function so that the user can type in what he or she is looking for and filter out the other options. 
    ```
12. What’s the difference between a button tag and an input tag with the attribute ‘type=”submit”’?
    ```
    They act the same, but a button tag allows you to input other html inside of it. A button could also be specified to be of type "reset" instead of its implicit type of "submit".
    ```
13. When would you use a textarea instead of an input with the attribute ‘type=”text”’?
    ```
    An input field is generally a one-line field wheras a textarea has multiple lines, so it can hold more text for things like addresses. 
    ```
14. What are semantic tags? Can you provide a few examples?
    ```
    Semantic tags are used for elements with meaning. For example, h1, form, footer, header, and nav.
    ```
15. What is an empty element, and what are some examples of empty elements?
    ```
    Empty elements are elements with no content (no end tag). Some examples include br, img, input, and meta. 
    ```
    
## CSS
1. What is a rule in CSS? What is a selector? What is a declaration block?
    ```
    CSS rules apply specific properties to some group of elements. A selector determines what type of element based on their name, id, class, etc. A decleration block assigns those properties in declarations. 
    ```
2. What are the ways you can make a declaration in a rule override another declaration in a rule with the same selector?
    ```
    Specificity is the weight applied to css delecrations. When multiple declarations have the same specificity, the last declaration in the CSS is used. Rules that directly target elements take precedence over rules inherited from rules applied to an element's ancestor. The selector types from least to greatest specificity is type, class, and id. In-line css can override css in css files. !important shouldn't be used but it can be used to override inline styles. 
    ```
3. How would you apply a border to the bottom of every list item (li) except the last in an unordered list? What is the construct called? Can you provide other examples of that construct and briefly explain what each does?
    ```
    li { border-bottom: 1px solid black; }
    li:last-child { border-bottom: none; }
    
    or 
    
    li:not(:last-child) { border-bottom: 1px solid black; }
    
    The construct is called a pseudo-class. 
    last-child: applies to last child in group of children elements
    first-child: applies to first child in group of children elements
    active: applies to element being activated by the user
    hover: applies to element with a pointing device but does not activate it (hover over with cursor)
    
    ```
4. How can you tell the difference between an element, ID and class selector? What is order of specificity (from least specific to most specific)?

    ```
    For element you just type in type of element, class uses "." and id uses "#". Order of specificity in number 2 .
    ```
5. If you apply position:absolute to a div, what is the result? How does it change if that same div is in another div with position:relative?
    ```
    The position:absolute element is positioned relative its first positioned non-static ancestor element. If it is not inside a div, this means its position is relative to the webpage borders. If it is in another div with position:relative, then it is relative to that ancestor div. 
    
    ```
6. How does position:fixed differ from position:absolute? When would you use fixed in lieu of absolute?
    ```
    Position fixed is always positioned relative to the browser window. Position: absolute is positioned relative to the nearest ancestor. You should used fixed if you don't want an element's position to be impacted by its ancestor. 
    ```
7. What are the key differentiators between a display value of block, inline, and inline-block?
    ```
    block: displays element as block element. Starts on new line, takes up whole width. 
    inline: displays element as inline element. Height and width properties have no effect.
    inline-block: element is formatted as inline element, but you can apply height and width properties. 
    inline-block allows padding and margins, but inline doesn't. 
    ```
8. What are some times where you should opt to use inline-block instead of inline?
    ```
    You should use inline-block if elements in the same line should have different widths and heights or need to have padding/margins.
    ```
9. What are the different values available for the float property? Does the float property work on inline elements? 
    ```
    none, left, right, initial, inherit. The float property turns inline elements into block elements. 
    ```
10. If all of an element’s children are floated, how does this affect the height of the element? What can you do to fix this?
    ```
    The height becomes 0. To fix this, you can add overflow: auto or float the element. 
    ```
11. What does it mean when you use the clear property?
    ```
    It specifies on which sides an element an element isn't allowed to float
    ```
12. What is the difference between inherit and initial?
    ```
    Initial uses the inital value defined. Inherit uses the initial value if the element has no parents but uses the parent's value if it does. 
    ```
13. Explain the HTML box model.
    ```
    All html elements are boxes that consist of margins, borders, padding, and content. 
    Content- content of the box (images, text, etc)
    Padding- clears area around content. Transparent
    Border- border that goes around the padding and content
    Margin- clears area outside of the border. Transparent
    ```
14. How does the box-sizing property affect the box model?
    ```
    box-sizing includes the padding and border in the element's total width and height. 
    ```
15. What does margin collapse mean? How does this affect elements with no content? How does this affect elements that are vertically stacked on top of each other?
    ```
    Margin collapsing means that the margins of two blocks are combined into a single margin that is the size of the largest margin between the two blocks. If an element has no content, border, padding, height, or min-height, then the top and bottom margins collapse. Elements that are vertically stacked on top of each other have top/bottom margins that collapse.
    ```
16. What are media queries? Why are they important in responsive web design?
    ```
    Media queries are used to modify the site based on the device's type or charateristics. They are important in responsive web design because they make the webpage more intuitive based on the charactersitics of the device that the user is viewing the webpage on. For example, screens of different widths should display their elements in different ways that make them easier to view for the user. 
    ```
## 
## Closure (aka Soy)
### **Setup**
1. Go to GitHub and create an empty repository under the Yext-Pages organization called “training-basics-[yourname]]”.
2. Open a terminal window and navigate to where you keep GitHub repositories.  
3. Follow GitHub’s instructions to clone the repo you just created via SSH and then navigate to that directory. 
4. Run the command “yo ysp:training”. This is the command line scaffolding tool known as “generator” that we use heavily for Pages, which you will use further during your final exam. 
5. Run “git add .” to stage all of the files added by generator, then run “git commit -m ’generated site’”.  
6. Run “git checkout -b media” to start a branch
7. Navigate to the src directory and run the command “grunt serve”.  The compilation process will begin, and after a few moments a browser window should open to the index of Pager.
8. Under the “Tasks” pane, click on the toggle switch next to “Proxy Mode” to turn off Proxy Mode (you don’t need to worry about what this does at this point)
9. Click on the “media.default” hyperlink under the “Templates” pane.  This will take you to a rendered version of the “default” template in src/template/media/media.soy Closure template.  The sample data used to render a template can be found in src/[fully-qualified-template-name].json, or src/media.default.json in this case.

For the following project, you’ll be editing the src/templates/media.soy file.  Following the project outline is a screen capture of a sample solution you’ll be working towards.

When you are finished, commit your changes and push your branch to GitHub.  Open a new Pull Request between your branch and master and assign your mentor as a reviewer.  After making any suggested changes and receiving approval, merge the Pull Request into master and sync locally.

Currently, we use an older version of Soy on our sites. You should reference the following documentation to familiarize yourself with Closure concepts and syntax that is compatible with the version we use:

1. [Concepts](https://web.archive.org/web/20140702051535/https://developers.google.com/closure/templates/docs/concepts)
2. [Commands](https://web.archive.org/web/20140326214855/https://developers.google.com/closure/templates/docs/commands)
3. [Functions and Print Directives](https://web.archive.org/web/20140702034718/https://developers.google.com/closure/templates/docs/functions_and_directives)


### **Exercise**

1. Define a template called ‘booklist’ in the namespace ‘media’ that takes 1 parameter: ‘books’. The ‘books’ parameter is an array of ‘book’ items. 
2. Each book has several properties, including title, authors, coverImageUrl, tags, description and publishDate. Define a template called ‘booklist_item’ that accepts all of the properties of a book and displays the information in a meaningful way. 
3. For each book in the ‘books’ parameter, invoke the ‘booklist_item’ template.
4. Some books do not have a cover image, so you need to make the coverImageUrl optional in the booklist_item template. In addition, to simplify the template, use the let command to redefine a new variable that coalesces a null coverImageUrl to the default url ‘http://bit.ly/1B1bPGC’.
5. Change your code so that only the first 3 tags for a given book are displayed. Make sure to account for the case where there are less than 3 tags.
6. Modify the template called ‘default’ so that it invokes the booklist template, passing the list of books as a parameter.
7. Some of the descriptions have line breaks to separate the paragraphs. Make sure that those line breaks are honored in the rendered output.
8. At the top of the book list, print out the number of books in the list.
9. Lastly, edit src/scss/default.scss (despite the file extension, you can use pure CSS) to style the markup so that it looks like the screenshot below.  Tweaks to the HTML may be required, but avoid putting too much presentation logic into the templates and avoid inline styles entirely.
    1. _Note:  There will be small delay before edits made to default.scss appear on on your page due to the SCSS -> CSS compilation process._

![alt_text](images/image13.png)

_Sample solution_
## 
## CSS Methodologies

There are [many different methodologies](http://sixrevisions.com/css/css-methodologies/) for writing CSS that define guidelines for how to structure and name your CSS. The goal of this section is to expose you to different popular methodologies. As a team, we have created our own style guide and use those standards across all of our projects. 

Before you learn about the specifics of our methodology, it’s important to understand what it’s based on. Our methodology was heavily influenced by SUIT. Please read [this article](http://mattfairbrass.com/2015/05/05/suit-css/) about it before answering the following questions.  

1. Explain the different naming conventions used in SUIT, and the significance of each. Specifically, focus on when you’d use each.
    ```
    Components: .ComponentName {}. written in pascal case. If it will be used by public projects, then prefix with namespace in lower case.
    Modifers: .ComponentName--modifierName{}. Modifiers are written in camel case with a double dash. Used when altering the base style of a component. Used in addition to the base component class.
    Descendants:  .ComponentName-descendentName {}. Used for descendents of components. Used directly on the descendent without the parent component class. Written in camel case with a single dash.
    Component State: .ComponentName.is-stateOfComponent{}. Used for adjoining classes that represent states of classes. States are written in camel case. Adjoining classes should not be styled directly. 
    Utilities: .u-utilityName{}. Written in camel case. Used for low-level positional and structural characteristics that should only do one thing. Can be applied to any element. 
    
    ```

2. In the following example, what is a component? What are the descendants? What modifiers do you see?
![alt_text](images/image11.png)
    ```
    Tweet is a component. Tweet-header, Tweet-avatar, Tweet-bodyText, and Tweet-button are descendants. Tweet-bodyText--main and Tweet-button--warning are modifiers. 
    ```
3. What are some benefits of using SUIT?
    ```
    It adds meaning to your CSS and makes it easier to maintain and change without encountering problems. You can move a component's css without breaking another component's styling and don't have to use !important. 
    ```
### **Legacy - SMACCS**

In the distant past, we used to use a different CSS Methodology called SMACCS, which you can read about [here](https://smacss.com/book/) (just skim through). SMACCS mostly focuses on how to structure your project-- how to name files, what types of styles to put in each, etc. When we first began using it, we didn’t really understand it, so we used a lot of very long class names, where elements were separated by dashes, which led to really long chains of nested SCSS. You’ll still see some aspects of SMACCS in our codebase: all of our sites use the file structure that SMACCS teaches, which we like, and older sites still follow this long class name paradigm that we don’t use anymore. 


### **Yext**

Now, read about Yext’s [CSS Methodology](https://docs.google.com/document/d/1rMdBjYe2m6aT9Jh7Xb9fPGR3G7miQVGYjohuJiB42sE). Our methodology looks a lot like SUIT, but it was informed by a lot of research and discussion among the team. The following isn’t required reading, but take a look at these articles that informed our research when we were creating the style guide:

*   [https://medium.com/objects-in-space/objects-in-space-f6f404727](https://medium.com/objects-in-space/objects-in-space-f6f404727)
*   [https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)

 

Here is an example of some code written in our old SMACCS framework:

![alt_text](images/image14.png)


And here is what the SCSS for this section looked like:

![alt_text](images/image12.png)


1. Please re-write the HTML using the Yext CSS Methodology.
    ```
    <div class = "AdvisorAbout">
        <div class = "AdvisorAbout-specifics">
            <div class = "AdvisorAbout-heading">
                {$heading}
            </div>
            <div class = "AdvisorAbout-text">
                {$text}
                <div class = "AdvisorAbout-text--small">
                    {$text}
                </div>
            </div>
        </div>
    </div>
    ```

2. Now that you’ve fixed this code, please describe what was wrong with it in the first place. Why do you think we stopped using SMACCS in favor of SUIT, and creating our own framework?
    ```
    With SMACCS, class names could be extremely long and also did not differentiate between components, descendants, and modifiers. 
    ```

3. In the repository from the Closure exercise, start a new branch called “new_css”.  Update your markup and CSS to reflect the methodologies laid out in the Yext docstyle, linked above.  Once finished, start another Pull Request, assign your mentor, and iterate until approval.  Merge the branch once complete.


## SCSS

1. What is SCSS and how is it different than CSS?
    ```
    CSS is a styling language. SCSS is a type of file for SASS, which is a Ruby program that assembles CSS for a browser. SASS allows for more functionality like variables and nesting. It also lets you import stylesheets into each other, create funcitons, and use math operations. 
    ```

2. What is nesting in SCSS and how does it help with style organization?
    ```
    Nesting is an easier way to write rules for nested elements. It makes it easier to see the hierarchy. 
    For example, instead of
    #locations ul li
        {
            color: red;
        }
    You can write
    #locations
    {
        ul
        {
            li
            {
                color: red;
            }
        }
    }
    ```

3. How do you add a pseudo-class to a parent selector with nesting?
    ```
    You use the '&' symbol to represent the outer parent selector. 
    Example: 
    .alert
    {
        &:hover
        {
            font-weight: bold;
        }
    }
}
    ```

4. How do you define a variable? How do you set a default value without overriding a previously set value? What operators can you use with variables?
    ```
    You use the '$' symbol. 
    Example:
    $base-color: #000000;
    
    You can add on !default to set a default value witout overriding a previously set value. 
    Example:
    $base-color: #000000 !default; 
    
    Operators you can use are :, +, -, *, /, %, ==, !=, >, >=, <, <=, and, or, not
    ```

5. How do you reference an external SCSS file?
    ```
    You use @import
    ```

6. What does @extend do? What does @include do? How do they differ? Are there certain places where you can’t use  @extend?
    ```
    @extend is used to share properties among different elements. @include lets you use mixins which can take arguments, unlike @extend. You should not use @extend for unrelated classes. @include also adds in the css everywhere it is used.
    ```

7. What is a mixin? How can you use one to simplify the inclusion of CSS properties that require browser prefixes?
    ```
    Mixins allow you to re-use the same attributes for different classes.  
    You can use a mixin like this:
    @mixin prefix($property, $value, $prefixes: ()) {
        @each $prefix in $prefixes {
            #{'-' + $prefix + '-' + $property}: $value;
        }
        #{$property}: $value;
    }
    ```

8. What is the difference between a function and a mixin?
    ```
    A function returns a value that can become a value for a css property if you want. A mixin ouputs lines of Sass code that will compile into css. 
    ```

## JavaScript

These days, Javascript is everywhere, from front-end web applications, to backend nodejs servers. Today, we’ll focus on some of the basics.



1. What are the different JS types? What are the falsy values for each?
    ```
    Number: 0, NaN
    String: ""
    Boolean: false
    Null: is a falsy
    Object
    Symbol
    undefined: is a falsy
    
    ```

2. What is the difference between var, let, and const?
    ```
    Var: they are globally scoped when outside of a function or locally scoped when inside of a function. They can be re-declared and updated. They can be accessed with a value of undefined even if they are declared later on in the code. 
    Let: variables are only defined within a block bounded by {}. They can be updated but not re-declared. You can't use a let variable before it is declared.
    Const: maintain constant values. They are only defined within a block bounded by {}. They can't be updated or re-declared. You can't use a const variable before it is declared. 
    
    ```

3. What is the difference between for...of and for...in?
    ```
    for...of iterates over the values/characters in an iterable (array/string). for...in iterates over properties of an object (object keys) or the index values of an iterable. 
    ```

4. What’s the difference between == and ===?
    ```
    == compares for equality after doing any necessary type conversions. === compares for equality without doing type conversions. Known as "type coercion."
    ```

5. What is a callback function?
    ```
    Function that executes after another function finishes executing that can be called by being passed as an argument. 
    ```

6. What is an anonymous function?  What is a closure?
    ```
    An anonymous function is a function without a name that can be stored within a variable. A closure makes a global variable local so that it can't be changed by other functions. It is a function that has access to the parent scope even after the parent function has closed. A closure is both a function and the environment in which it was created.
    ```

7. Write a function that given an array of integers outputs the total sum of each odd number squared. For example, given x = [1, 2, 3], the output would be 10.
    ```
    function sum(array)
    {
        var total = 0;
        for(let i of array)
        {
            if(i%2 == 1){
                total+=i*i;
            }
        }
    }
    ```

8. Describe the map, reduce, and filter functions and their uses.
    ```
    Map takes a callback function as an argument, which runs on each item in the array, and returns the new values in the new array. For example, this could be used if you needed to multiply each number in an array by 3. Reduce also runs a callback function on each element of an array and returns a single value. For example, this could be used if you needed to add the squares of every number in an array. Filter creates a new array with only the items of an array that match some parameter. For example, you could return an array of the ages of adults at a party from an array of the ages of party guesets that include adults and children. 
    ```

9. Rewrite your function from the above question using a combo or subset of map/reduce/filter.
    ```
    function sum(array)
    {
        var oddArray = array.filter(function(num){
            return num%2 == 1;
        });
        var squaredArray = oddArray.map(function(num){
            return num*num;
        });
        return squaredArray.reduce(function(total, num){
            return total + num;
        },0);
    }
    ```

10. What is the difference between using require() and import?
    ```
    Require: Dynamic loading wherever the module named isn't predefined and loading is synchronous. 
    Import: Load solely the items you want, asynchronous, can't be used with Node. 
    ```

11. How do you declare a default parameter for a function?
    ```
    Inside the function parenthesis like this: 
    function something(word = "hi")
    {
    console.log(word);
    }
    ```

12. What are some different ways of using the DOM API to grab HTML elements on a page?
    ```
    document.getElementsByTagName(name)
    document.getElementById(id)
    document.getElementByName(name)
    document.getElementsByClassName(name)
    document.querySelector(selectors)
    document.querySelectorAll(selectors)
    ```

13. Write a command to find all elements in this codepen with the class name .Button--main (https://codepen.io/anon/pen/MVbOdG)
    ```
    var x = document.getElementsByClassName("Button--main");
    ```

14. Write a function using the previous codepen that logs “Hello!” every time one of the Button--main elements is clicked on
    ```
    var x = document.getElementByClassName("Button--main")
    for(let i of x)
    {
        i.onclick = function sayHello()
        {
            console.log("Hello!");
        };
    }
    ```

15. What’s the difference between ‘async,’ ‘defer,’ and using neither?
    ```
    When using neither, the html parsing pauses to fetch and execute any javascript elements that are in the html file. 
    When using async, the html parsing continues while the javascript is being fetched at the same time. The html parsing pauses while the javascript is being executed. 
    When using defer, the html parsing continues while the javascript is being fetched at the same time. The javascript is only executed after html parsing is completed.
    ```

16. Does the ordering of imported JavaScript files matter? Why or why not?
    ```
    Order matters. If you have a function within a javascript file, you can't call that function without importing the file first. 
    ```

17. What does AJAX stand for and what is its purpose? Provide an example of when you would want to use AJAX.
    ```
    AJAX stands for Asynchronous Javascript and XML. It is a technique to create faster and more interactive web apps. It allows the user to do something like fill out a form or press a button, after which javascript will send and get information from the server and update the webpage without having to reload it. An example would be if a user wanted to find all available flights to Paris and clicked a button to search and a list of all available flights popped up on the screen. 
    ```

18. Describe CORS and its relevance to web security. When might CORS come up in practice?
    ```
    CORS manages cross-origin requests, which are requests for resources outside of the origin (different server). CORS allows servers to specify which origins can access assets on the server and how (get, patch, put, delete).  This is useful because it prevents people from accessing your server and behaving maliciously, such as deleting all of your assets. 
    ```

### **Exercise**

For a more in-depth look at the most recent version of Javascript, please read the article on this GitHub page: [https://github.com/lukehoban/es6features](https://github.com/lukehoban/es6features).

Create a [Codepen](http://codepen.io) for your code, and update it as you go through the steps. You can make a personal account to save your “pens”, or just save this one as anonymous. Write your code in the “JavaScript” pane (you can collapse the other two to make it easier to read), and test by hitting save and pulling up the console. **Make sure that the code compiles and works as expected.**



1. Define a class called ‘Element’ that has a constructor that takes a single parameter called ‘mass’. Set a property called ‘mass’ on the class equal to the passed in parameter.
2. Add a method to the class called ‘hitWithHammer’ that sets a property called ‘status’ to “unknown”.
3. Add a method to the class called ‘describe’. The method should return a string containing the name and the current status that was built with interpolation.
4. Create three other classes called ‘Diamond’, ‘Aluminum’ and ‘Tellurium’ that extend Element. Override the hitWithHammer method and set the status to ‘unchanged’, ‘dented’ and ‘shattered’, respectively.
5. Set a property called ‘name’ in the constructor for each object, and set the name of the object to the class name. Don’t forget to invoke the super constructor first.
6. Define an array of Diamond, Aluminum, and Tellurium objects called thingsToSmash.
7. Use a loop to hit each object in thingsToSmash with a hammer.
8. Use the describe method to print out the elements
    ```
    Link to codepen: https://codepen.io/rachelnaidich/pen/gNqGap?editors=1111
    ```

## Interacting with the DOM

jQuery is a commonly used JavaScript framework that we use in our Pages products.

1. What are the different jQuery ways of determining DOMContentLoaded?
    ```
    jQuery.ready
    $.ready
    $
    
    ```

2. What does $.on do? When should you use it?
    ```
    It attatches event handlers to elements. For example, you can make some function run when an element is clicked. 
    ```

3. How would you find all links with a class of ‘yext’?
    ```
    $("a.yext")
    ```

4. Using your answer from question 3, append a query parameter called ‘campaignId’ with a value of ‘123’ to each link.
    ```
    $("a.yext").attr('href', function()
    {
        return this.href + '?campaignId=123';
    })
    ```

5. How would you find an input element by its name attribute?
    ```
    $("input[name*='value']")
    ```

6. How would you find the value(s) of a selected checkbox?
    ```
    var values = [];
    $('input:checked').each(function(index, element) {
        values.push(element.val());
    });
    ```

7. How would you add an event listener to an element using jQuery? Write a function in jQuery this time to print “Hello!” when any of the Button--main elements are clicked
    ```
    $(".Button--main").click(function()
    {
        console.log("Hello!");
    });
    ```

8. What are some differences between using the DOM api to grab elements or add an event listener, and using jQuery?
    ```
        If I want to grab elements, I can be more specific and combine attirbutes when using jQuery but not with the DOM api. Adding an event listener to multiple elements with the same attribute such as the same class name is easier with jQuery. 
    ```

## CoffeeScript
We used to write in CoffeeScript instead of Javascript because some of the features it offered. After the ES6 release, we’re now transitioning back to pure Javascript development, but you’ll still see some .coffee files sprinkled in old sites. You can read more about coffeescript on our [legacy page](https://sites.google.com/yext.com/consulting-engineering/pages/legacy?authuser=0).

## SEO
Pages is an important product for our clients because it allows each one of their locations to have original content and get crawled/indexed by search engines. Having these locations SEO allows people to easily find our clients and get to the places they are looking for.


1. What does SEO stand for and why is it important?
    ```
    SEO stands for Search Engine Optimization. It is important because it improves your website's search engine rankings and makes it more competitive against other websites. 
    ```

2. What is a canonical link? Give an example.
    ```
    A canonical link is an html element that tells search engines that some similar URLs are actually the same so that it doesn't harm your search engine rankings. One example that could use a canonical link is if you have two web pages with the exact same content but in separate sections of your site with maybe different layouts. 
    ```

3. What is an hreflang tag? Give an example.
    ```
    An hreflang tag tells the search engine which language you are using on a specific page so that it will give your website as a result to people who searched in your language. 
    Example: 
    
    <link rel="alternate" href="http://example.com" hreflang="es-es" />
    <link rel="alternate" href="http://example.com/fr/" hreflang="fr-fr" />
    <link rel="alternate" href="http://example.com/pt/" hreflang="pt-pt" />
    ```

4. What is robots.txt used for? Give an example of a simple robots file that allows all except for the ‘restricted’ folder.
    ```
    A robots.txt file tells the search engine which pages it can request from your site so that it is not overloaded with requests. 
    
    User-agent: *
    Disallow: /restricted/
    ```

5. How are meta tags used to help with SEO?
    ```
    They make it easier for search engines to deterine what your content is about.
    You can include tags like a title tag and a description.
    ```

6. Describe some techniques for improving SEO performance. This should be a short list of things you could do, rather than an exhaustive list.
    ```
    1. improve user experience on site
    2. improve load speed
    3. optimize images (format, sizing, keywords for image file name, alt tag, description, caption)
    4. Good header tags
    5. Links to well-respected sites/no broken links
    6. Different multimedia
    
    ```

7. Who in the office is the SEO guru?
    ```
    Lenny
    ```

8. What is structured data (aka Google’s schema.org) and why is it important?
    ```
    Structured data is code in a format that is understandable to search engines. It is important because it provides more details and makes your result look better for your specific type of webpage. For example, there's structured data for books, reviews, movies, products, and more. 
    ```

9. One of the main ways our pages communicate with search engines is through schema tagging. Specifically, we use tagging defined on Schema.org, as a way to mark up the information on our pages to be more SEO (Search Engine Optimization) friendly. Write a snippet of HTML that uses schema.org tagging to decorate a simple page for a local business. Include their address, phone number, an upcoming event held at their location, and a short blurb about their manager.
    ```
    <div itemscope itemtype = "http:schema.org/LocalBusiness">
        <div>Address: <span itemprop="adddress">666 Fakename St, Fakesville, VA 66666</span></div>
        <div>Phone number: <span itemprop="telephone">(666)-666-6666</span></div>
        <div itemprop="event" itemscope itemtype="http:schema.org/Event">
            <div itemprop="name">Summer Party></div>
            <meta itemprop="startDate" content="2016-06-15" />Start date: June 15 2019
            <meta itemprop="endDate" content="2016-06-17" />End date: June 17 2019
        </div>
        <div itemprop="founder" itemscope itemtype = "http:schema.org/Person">
            <div>Our founder: <span itemprop="givenName">Michael </span><span itemprop="familyName">Scott</span></div>
            <div>Michael is the <span itemprop="jobTitle">CEO </span> of this business. He is from <span itemprop="birthPlace">Michigan</span>.</div>
        </div>
    </div>
    ```

## 
## Grids & Layouts

There are several popular frameworks and techniques that can be used to place content on the page. The best of these easily allow for reordering or reshaping of content at different breakpoints. In the past, used Bootstrap as our main framework, but have stopped using it in favor of Flexbox layouts and CSS Grid.

[Read this article](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids) to familiarize yourself with the fundamentals of a grid layout and answer the following questions:


1. Why are grids useful for web development?
    ```
    Grids serve as a basic structure for your the elements on your webpage for easy positioning. 
    ```

2. What are the typical elements of every grid layout? Describe what each of them means in the context of the grid. 
    ```
    Rows: horizontal lines of a grid
    Columns: vertical lines of a grid
    Gutters: spaces between each column/row
    
    ```

3. What is the difference between a fixed grid and a fluid grid? Why is one better than the other?
    ```
    Fixed: has a fixed width in pixels independent of screen size
    Fluid: size is specified by percentages, so proportion of the elements stay the same if the screen size changes. 
    Fluid is better than fixed because it adjusts based on what size screen the user is using. 
    ```

4. Write the CSS classes for .row and .col that you would need to implement your own grid of 8 columns, with 30px gutters.
    ```
    .col
    {
        float: left;
        margin-right: 15px;
        margin-left: 15px;
        width: 12.5%;
    }
    
    .row
    {
        margin-bottom: 15px;
        margin-top: 15px;
    }
    ```

5. What is the difference between semantic and unsemantic grids? Give an example of how you would implement both.  Why might you use one vs the other?
    ```
    Unsemantic: describing how the content looks
    Semantic: describes the content
    You could use unsemantic grids when you have multiple elements that should all be positioned and sized similarly but have different content and/or styling.
    You could use semantic grids when most of your elements are unique and need to be positioned and sized separately. 
    
    You can implement both by copying the sizing rules from a unsemantic class into a semantic class. 
    
    ```

6. Why does the article say Flexbox was never designed as a grid layout?
    ```
    Flexbox was never designed as a grid layout because it is one-dimensional. 
    ```

7. What is CSS grid and why is it significant?
    ```
    CSS grid is a layout system for webpages that lets you lay out elements in rows in columns that makes it easy to position them. 
    ```

Below we will dive into both Flexbox and CSS Grid.

### **Legacy - Bootstrap V3**

We used to make heavy use of Twitter Bootstrap on our Pages. We used it because it allowed us to implement a robust responsive grid system on our webpages quickly. The introduction of Flexbox (see below) and CSS grid made independent frameworks like Bootstrap no longer necessary, and today we rely on native CSS for Flexbox and CSS Grid, in addition to utility helpers that we have built into our codebase, which you’ll get to explore in the final module of your training.


### **Flexbox**

The flexbox layout consists of a few simple css rules that can be used to order, align, and distribute elements. Many times in our Pages sites the order of elements need to be switched or elements need to be evenly distributed - and flexbox helps us do that. Read more about flexbox [here](https://css-tricks.com/snippets/css/a-guide-to-flexbox/).

To learn how to use flexbox please play [this game](http://flexboxfroggy.com/) and paste a screenshot of the completion screen below.
![alt_text](images/screenshot.png)
Please make use of Flexbox to solve the following code problems. Please create a new codepen for each of these responses, and include the link in the box below.


1. We continue to use Bootstrap 3’s responsive breakpoints in our projects to differentiate between different screen sizes. What are Bootstrap 3’s default responsive breakpoints?
    ```
    // Extra small devices (portrait phones, less than 576px)
    // No media query since this is the default in Bootstrap
    
    // Small devices (landscape phones, 576px and up)
    @media (min-width: 576px) { ... }
    
    // Medium devices (tablets, 768px and up)
    @media (min-width: 768px) { ... }
    
    // Large devices (desktops, 992px and up)
    @media (min-width: 992px) { ... }
    
    // Extra large devices (large desktops, 1200px and up)
    @media (min-width: 1200px) { ... }
    ```

2. Write the HTML and CSS to build the Flexbox Layout 1 shown below.
    ![alt_text](images/image15.png)
    ```
    Link to codepen:https://codepen.io/rachelnaidich/pen/JQzMjb
    ```

3. Modify your code that you wrote above so that in XS it looks like Flexbox Layout 2, but for all other breakpoints it looks like Flexbox Layout 1.
    ![alt_text](images/image16.png)
    ```
    Link to codepen: https://codepen.io/rachelnaidich/pen/ZdPRze
    ```

4. Now make it so that in XS, it looks like FlexboxLayout 3’ but for all other breakpoints it looks like Flexbox Layout 1.
    ![alt_text](images/image17.png)
    ```
    Link to codepen: https://codepen.io/rachelnaidich/pen/PrLaKq
    ```

### **CSS Grid**

CSS Grid is a two-dimensional grid system that gives us a method of creating grid structures that are described in CSS and not in HTML. Please read more about it [here](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Basic_Concepts_of_Grid_Layout).

To learn how to use CSS Grid, please play [this game](http://cssgridgarden.com/) and paste a screenshot of the completion screen below.
![alt_text](images/screenshot2.png)


5. Use CSS Grid (no flexbox) to implement the following layout so that in XS it looks like Flexbox Layout 1, but for all other breakpoints it looks like CSS Grid Layout 1.
    ![alt_text](images/image18.png)
    ```
    Link to codepen: https://codepen.io/rachelnaidich/pen/LKaBxE
    ```

This concludes ‘The Basics’ module.
