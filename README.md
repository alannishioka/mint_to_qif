# JavaScript Mint CSV to Quicken QIF Converter

Convert CSV file of transactions to QIF for import into Quicken

## Usage: [http://nishioka.com/mint_to_qif.html](http://nishioka.com/mint_to_qif.html)

## Notes:

* If you select multiple files, any duplicate transactions will be ignored.  (Duplicate transactions have the same date, description and amount)
* So you can select the files from the previous two months, and only new transactions will be output.
* Account is entered in the memo field.
* Category is left blank because Mint categories are different from Quicken.
* This program runs in JavaScript entirely within your browser.  No data is sent anywhere.  (Your browser may save data in the cache and downloads directory.)
* This program has been to tested to work on Quicken 2016, Chrome 74, Edge 42, Firefox 66, Internet Explorer 11, Opera 60, Safari 12.

## This program uses:

* FileReader to read from local filesystem
* Recursive function to handle callback hell
* Blob to write to local filesystem
* QIF file format
* A custom compare function to sort an array of objects
* An O(nlogn) algorithm to only output unique items
* No external libraries
* Internet Explorer compatible JavaScript

## Changes:
* d3.csv to parse CSV replaced with function so no external libraries.
* for..of replaced with for loop for Internet Explorer
* Promise.all replaced with recursive function for Internet Explorer
* Replaced arrow notation because I hate it.
