# Key Capture and Display Program

This is a simple HTML and JavaScript program that captures a key press event and displays information about the pressed key, including its key value, keycode, and code. The program uses a parent-child div structure to create a centered display area.

## Table of Contents

- [Introduction](#introduction)
- [Usage](#usage)
- [CSS Styles](#css-styles)
- [JavaScript Logic](#javascript-logic)

## Introduction

This program demonstrates how to capture key press events and display information about the pressed key. The HTML structure consists of a parent div that is centered on the page and a child div that initially displays the message "Press Any Key." When a key is pressed, the child div is updated to display a table containing details about the pressed key, including its key value, keycode, and code.

## Usage

To use this program, follow these steps:

1. Create an HTML file.
2. Copy the HTML and JavaScript code provided in this `readme.md` file into your HTML file.
3. Open the HTML file in a web browser.
4. Press any key on your keyboard to see the information about the pressed key displayed in a table format within the child div.

## CSS Styles

The program uses CSS to style the layout and appearance of the displayed content. Some key styles applied are:

- `.parent`: Styles the parent div as a flex container, centering its content both horizontally and vertically.
- `.child`: Styles the child div, setting text color, padding, font size, and font style.
- `.color`: Defines the color of the text within the displayed table.
- `table`: Styles the table, setting border-collapse and width properties.
- `th, td`: Styles the table header and cells, setting border and padding properties.
- `th`: Defines the background color of the table header.

## JavaScript Logic

The JavaScript code captures keydown events using the `addEventListener` method. When a key is pressed, it updates the content of the child div with a dynamically generated table that displays the pressed key's key value, keycode, and code. The template literal syntax is used to construct the HTML table structure.

```javascript
let toShowData = document.querySelector('.parent');

document.addEventListener('keydown', (e) => {
  toShowData.innerHTML = `
    <div class="color">
    <table>
    <tr>
      <th>Key</th>
      <th>Keycode</th> 
      <th>Code</th>
    </tr>
    <tr>
      <td>${e.key === ' ' ? 'Space' : e.key}</td>
      <td>${e.keyCode}</td> 
      <td>${e.code}</td>
    </tr>
  </table>
    </div>
  `;
});
