# Uncommon HTML Bug: Asynchronous Event Listener

This repository demonstrates a subtle bug in HTML involving event listeners and the order of DOM manipulation.  The issue highlights the importance of ensuring that elements exist in the DOM before attaching event listeners.

## Bug Description

The bug lies in attaching an event listener to an element ("myDiv") before the element is fully added to the Document Object Model (DOM).  In this case, the event listener is added within a `<script>` tag that executes before the element is rendered. This results in the event listener not being attached correctly, causing the expected "alert" message to not appear upon clicking the div.

## How to Reproduce

1. Clone this repository.
2. Open `bug.html` in a web browser.
3. Click the div. The alert message will not appear because the event listener failed to attach.

## Solution

The solution involves ensuring the element exists in the DOM before attaching the event listener. We can achieve this by either:

* Placing the script tag after the "myDiv" element in the HTML or
* Using `DOMContentLoaded` event to ensure that the page is fully loaded before attaching the event listener

The `bugSolution.html` file provides the corrected code.
