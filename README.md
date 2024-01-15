# Mint CSV to Quicken QIF Converter (JavaScript)

Convert CSV file of transactions to QIF for import into Quicken

## Usage: [http://nishioka.com/mint_to_qif.html](http://nishioka.com/mint_to_qif.html)

## Notes:

* If you select multiple files, you can UNcheck Allow Duplicates so that duplicate transactions will be ignored. (Duplicate transactions have the same account, date, description and amount, WARNING this WILL ignore transactions that appear on the same day with same amount)
* So you can select the files from the previous two months, and only new transactions will be output.
* If you include account name, the transaction will be imported into a Quicken account of **exactly** the same name.
* If you don't include account name, the transactions must be imported into a Quicken cash account.
* Warning: Mint exports pending transactions, but does not include them in account totals.
* This program runs in JavaScript entirely within your browser.  No data is sent anywhere.
* This program has been to tested to work on Quicken 2024, Chrome 120, Edge 42, Firefox 66, Internet Explorer 11, Opera 60, Safari 12.

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
* added ability to import tags, and specify predefined tags to allow multiple tags per transaction.
* correctly handles importing notes longer than 63 characters.
* d3.csv to parse CSV replaced with function so no external libraries.
* for..of replaced with for loop for Internet Explorer
* Promise.all replaced with recursive function for Internet Explorer
* Replaced arrow notation because I hate it.
* Added checkbox for account, category, notes
