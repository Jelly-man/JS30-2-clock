﻿# JS30-2-clock

Clock Hand Rotation
This project from Wes Bos 30 days of Javascript showcases how to rotate a clock's second hand using JavaScript and CSS transformations.

![Image of Javascript clock](image.png)

Description
The line of code secondHand.style.transform = rotate(${secondsDegrees}deg) is used to rotate the second hand of a clock based on the current time. This snippet applies a CSS transform to rotate the second hand by the calculated degrees.

Key Code Breakdown
javascript

secondHand.style.transform = `rotate(${secondsDegrees}deg)`;
secondHand: This is a reference to the DOM element representing the second hand of the clock.
style.transform: A CSS property that applies 2D or 3D transformations to an element. In this case, we're using it to rotate the second hand.
rotate(${secondsDegrees}deg): A function that rotates the element by the value of secondsDegrees. The deg unit is for degrees of rotation.
How the Rotation Works
The clock works by determining how many degrees to rotate the second hand based on the current second of the minute. Here's a breakdown:

A full rotation (360 degrees) represents 60 seconds.
Each second advances the second hand by 6 degrees (since 360 degrees / 60 seconds = 6 degrees per second).
For example, when the seconds value is 15, the hand rotates by 15 \* 6 = 90 degrees.

Example
Here's how you might set this up within a function that calculates the current time and rotates the second hand accordingly:

javascript

const secondHand = document.querySelector('.second-hand');

function setClock() {
const now = new Date();
const seconds = now.getSeconds();
const secondsDegrees = ((seconds / 60) \* 360) + 90; // Offset for starting point
secondHand.style.transform = `rotate(${secondsDegrees}deg)`;
}

setInterval(setClock, 1000); // Update every second

Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/clock-rotation.git
Open the index.html file in your browser to see the clock in action.

Usage
This code can be used to create a simple analog clock where the second hand rotates based on real-time calculations.
