---
layout: page
title: About
permalink: /about/
---

<style>
    /* Style looks pretty compact, trace grid-container and grid-item in the code */
    .grid-container {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); /* Dynamic columns */
        gap: 10px;
    }
    .grid-item {
        text-align: center;
    }
    .grid-item img {
        width: 100%;
        height: 100px; /* Fixed height for uniformity */
        object-fit: contain; /* Ensure the image fits within the fixed height */
    }
    .grid-item p {
        margin: 5px 0; /* Add some margin for spacing */
    }
</style>

<!-- This grid_container class is for the CSS styling, the id is for JavaScript connection -->
<div class="grid-container" id="grid_container">
    <!-- content will be added here by JavaScript -->
</div>

<script>
    // 1. Make a connection to the HTML container defined in the HTML div
    var container = document.getElementById("grid_container"); // This container connects to the HTML div

    // 2. Define a JavaScript object for our http source and our data rows for the Living in the World grid
    var http_source = "https://upload.wikimedia.org/wikipedia/commons/";
    var living_in_the_world = [
        {"flag": "0/01/Flag_of_California.svg", "greeting": "Hey", "description": "California - for now"},
        {"flag": "a/ac/Flag_of_Indiana.svg", "greeting": "Hi", "description": "Indiana - 7 years"},
        {"flag": "0/09/Flag_of_South_Korea.svg", "greeting": "안녕", "description": "South_Korea - 3 years"},
    ]; 



 
    // 3a. Consider how to update style count for size of container
    // The grid-template-columns has been defined as dynamic with auto-fill and minmax

    // 3b. Build grid items inside of our container for each row of data
    for (const location of living_in_the_world) {
        // Create a "div" with "class grid-item" for each row
        var gridItem = document.createElement("div");
        gridItem.className = "grid-item";  // This class name connects the gridItem to the CSS style elements
        // Add "img" HTML tag for the flag
        var img = document.createElement("img");
        img.src = http_source + location.flag; // concatenate the source and flag
        img.alt = location.flag + " Flag"; // add alt text for accessibility

        // Add "p" HTML tag for the description
        var description = document.createElement("p");
        description.textContent = location.description; // extract the description

        // Add "p" HTML tag for the greeting
        var greeting = document.createElement("p");
        greeting.textContent = location.greeting;  // extract the greeting

        // Append img and p HTML tags to the grid item DIV
        gridItem.appendChild(img);
        gridItem.appendChild(description);
        gridItem.appendChild(greeting);

        // Append the grid item DIV to the container DIV
        container.appendChild(gridItem);
    }
</script>


### My life
* Born 2010
* Come to Indiana 2013
* Go to elementary school 2015-2019
* Move to LA 2019
* Go to elementary school 2019-2020
* Move to San Diego 2020
* Go to elementary school 2020-2021
* Go to middle school 2021-2024

### Intrests and disintrests
I like playing video games and reading books. I enjoy play board games with my family. I like k-pop. I like watching baseball, tennis, and golf. I dislike doing what my parents tell me to do. I dislike playing sports.

<script src="https://utteranc.es/client.js"
        repo="Hello12345678890/hamin"
        issue-term="pathname"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>
