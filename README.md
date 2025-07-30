# Jameson Ho - Web Crawler

## High-Level Approach

The Web Crawler gathers and traverses pages/links on a website. First, it logs a user into their account on the website and cycles through every link as it finds them, keeping track of what it has already went through and what is left in the queue. In each page, it searches its HTML to look for secret flags, logging the contents of the flag and how many flags it has seen. It does this until 5 flags are found and then the program is terminated.

## Challenges Faced

One of the main challenges I faced was figuring out how to maximize performance. My original implementation did not utilize a end-of-message delimiter so it took forever each crawl that it did because it did not know when the message/data ended. To fix this, I utilized the content-length value in the response in order to determine when all the data that was sent has been receieved. Another challenge that I ran into was figuring out how to process and extract the a tags on each page because I first had to examine the HTML myself using inspect element and then figuring out exactly what I was looking for. Once I figured this out, it was much more simple.

## Testing Overview

To test my client, I first made sure that I was able to login successfully by printing the response from server (expected: 302). After this, I started to work on the implementation for the traversing/crawling, and I had to write a lot of print statements throughout my process of coding in order to debug and figure out what was going on at any given moment. For example, I made sure to check the queue, found flags, current link on, etc.
