<template>
    <div class="flex-container">
        <div>
            <h2>1. My Personal Profile</h2>
            <p>Welcome to my personal profile! Here, you'll learn a little bit about my education, experiences, hobbies, and dreams.</p>
        </div>
 
        <div>
            <h2>2. Education / Achievements</h2>
            <ul>
                <li>Graduated from senior high school at APC in Makati City.</li>
            </ul>
        </div>
 
        <div>
            <h2>3. Course</h2>
            <p>I am currently studying BS Computer Science specializing in Software Systems.</p>
        </div>
 
        <div>
            <h2>4. IT Experience</h2>
            <ul>
                <li>No experience in programming, just played sports and tried playing competitively in League of Legends for a year.</li>
            </ul>
        </div>
 
        <div>
            <h2>5. Hobbies & Interests</h2>
            <ul>
                <li>Basketball, swimming, running, RC racing, taking care of 2 dogs, 2 cats, and 2 ducks, reptile keeping (Leopard Tortoise, Sulcata Tortoise, Indian Star Tortoise), sneaker collecting, and teasing friends.</li>
            </ul>
        </div>
 
        <div>
            <h2>6. Goals In Life / Dream</h2>
            <p>My goal in life is to be rich enough to make a home for the elderly. As a family, my cousins and I aim to achieve collective wealth. My dream is to be the best son to my parents, the best husband to my wife, and the best for God.</p>
        </div>
 
        <div>
            <h2>7. Picture Gallery</h2>
            <table border="1">
                <tr>
                    <td><img src="https://raw.githubusercontent.com/Airo0429/WEBPROG-SS231-Personal-Website/main/Isaiah%204110.png" alt="Image" width="500" height="333"></td>
                </tr>
            </table>
        </div>
    </div>
 
    <div id="app">
        {{ message }} <br>
        {{'Random number: ' + Math.ceil(Math.random()*6) }}
        <div v-bind:class="vueClass">This element is bound to the "pinkBG" class.</div>
    </div>

    <div id="app2">
        <div>
            <figure v-for="x in manyFoods">
                <img v-bind:src="x.url">
                <figcaption>{{ x.name }}</figcaption>
            </figure>
        </div>
    </div> <!-- Closing for #app2 -->

    <div id="app3">
        <form v-on:submit.prevent="addItem">
            <p>
                What do you need? <br>
                <input type="text" required placeholder="item name.." v-model="itemName">
            </p>
            <p>
                How many? <br>
                <input type="number" placeholder="number of items.." v-model="itemNumber">
            </p>
            <p>
                Important?
                <label>
                    <input type="checkbox" v-model="itemImportant">
                    {{ itemImportant }}
                </label>
            </p>
            <button type="submit">Add item</button>
        </form>
        <br>
        <hr>
     
        <div>
            <p><strong>Shopping list:</strong></p>
            <ul id="ulToFind">
                <li 
                    v-for="item in shoppingList" 
                    v-bind:class="{ impClass: item.important }"
                    v-on:click="item.found=!item.found"
                    v-show="!item.found">
                    {{ item.name }}, {{ item.number }}
                </li>
            </ul>
            <ul id="ulFound">
                <li 
                    v-for="item in shoppingList" 
                    v-bind:class="{ impClass: item.important }"
                    v-on:click="item.found=!item.found"
                    v-show="item.found">
                    {{ item.name }}, {{ item.number }}
                </li>
            </ul>
        </div>
    </div> <!-- Closing for #app3 -->
</template>

<script></script>
<style></style>
