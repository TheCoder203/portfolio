---
layout: post
title: About
permalink: /about/
comments: true
---

## As a conversation Starter

![My Photo](/images/my_photo.jpg)

Here are some places I have visited.

<comment>
Flags are made using Wikipedia images
</comment>

<style>
    /* Style looks pretty compact, 
       - grid-container and grid-item are referenced the code 
    */
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

    .image-gallery {
        display: flex;
        flex-wrap: nowrap;
        overflow-x: auto;
        gap: 10px;
        }

    .image-gallery img {
        max-height: 150px;
        object-fit: cover;
        border-radius: 5px;
    }
</style>

<!-- This grid_container class is used by CSS styling and the id is used by JavaScript connection -->
<div class="grid-container" id="grid_container">
    <!-- content will be added here by JavaScript -->
</div>

<script>
    // 1. Make a connection to the HTML container defined in the HTML div
    var container = document.getElementById("grid_container"); // This container connects to the HTML div

    // 2. Define a JavaScript object for our http source and our data rows for the Living in the World grid
    var http_source = "https://commons.wikimedia.org/wiki/Special:FilePath/";
    var living_in_the_world = [
        {"flag": "Flag_of_California.svg", "greeting": "Howdy", "description": "California - forever"},
        {"flag": "Flag_of_India.svg", "greeting": "Namaste", "description": "India"},
        {"flag": "Flag_of_France.svg", "greeting": "Salut", "description": "France"},
        {"flag": "Flag_of_Mexico.svg", "greeting": "Hola", "description": "Mexico"},
        {"flag": "Flag_of_England.svg", "greeting": "Hi", "description": "England"},
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
        img.src = http_source + encodeURIComponent(location.flag); // build a reliable Wikimedia file URL
        img.alt = location.description + " Flag"; // add alt text for accessibility

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

### Journey through Life

Here is what I did at those places

- I was born in San Diego
- 🏫 Went to Monterey Ridge for transitional kindergarten - 4th grade
- 🏫 Went to Del Sur for 5th grade
- 🏫 Went to Oak Valley for 6th through 8th grade.
- 🏫 Going to Del Norte for 9th grade.


### Gallery of Pics of where I've been

<div class="image-gallery">
  <img src="https://commons.wikimedia.org/wiki/Special:FilePath/El_Castillo_de_Chich%C3%A9n_Itz%C3%A1.jpg" alt="Chichén Itzá">
  <img src="https://commons.wikimedia.org/wiki/Special:FilePath/Taj_Mahal_2012.jpg" alt="Taj Mahal">
  <img src="https://commons.wikimedia.org/wiki/Special:FilePath/Buckingham_Palace,_London_-_April_2009.jpg" alt="Buckingham Palace">
  <img src="https://commons.wikimedia.org/wiki/Special:FilePath/GoldenGateBridge.jpg" alt="Golden Gate Bridge">
  <img src="{{site.baseurl}}/images/about/img_0179.jpg" alt="img_0179">
</div>



