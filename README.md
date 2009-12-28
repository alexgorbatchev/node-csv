CSV
===

A CSV parser for node.js that will parse provided text data or stream parse a file. This allows you to process large files efficiently and using the raw power of node.js's event system.

API
---

`var csv = require('./lib/csv');`

Imports the CSV parser into your code for use under the variable named 'csv'. Use this to access the functions within the CSV parser.

`csv.each('file.csv')`

Opens and stream parses a CSV file provided by the first argument value. The second argument can be an _options_ object with the following attributes:

  * _headers_: true or false values expected, if true the first row of the provided file will be used as headers and not emitted as data. Furthermore all other rows within the CSV will be converted from array objects to new objects with attributes identified in the headers row.
  * _strDelimiter_: String delimiter that is used to separate data values within the file. Default is ",", but can be any value.
  * _readAmount_: Number of bytes to read on each cycle. The smaller the value, the faster the 'data' event is emitted, but it will be more processor and memory intensive. Default is recommended.

`csv.parse("a,b,c,e,f\nk,l,m,s,d")`

Parses a string CSV value and emits 'data' events. Second argument can be an options object with the same attributes as above.