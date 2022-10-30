# AuroDigital

Here's a understanding of the question and the flow I think of implementing to complete the problem:

Reads a file with fictional orders
Read all the orders in the orderfiles, and maintain order book

order messages as read and processed.
Types of orders ->
AddOrder , DeleteOrder

Order book maintained in memory -> ram -> no db -> dictionaries

Stored on basis of price and time

At start and end of processing, timestamp should be outputted -> time.now() , time.since()

All order books should be printed at the end, along with duration of processing (in seconds) -> time.since for each book

Data consistency -> multithreaded ->
1. mutual exclusion locks, when accessing shared memory -> dictionary , one acces at a time
2. do once function, in case each order creates a separate order book , instead of checking for an already existing one


Use order as key , starting time, last processed time , lastprocesss-starttime = processing time
(Use multiple maps, with identical keys)

Orderbook -> Name of a book -> orders placed for that book-author-combo
Class -> Object -> maps, methods, fields of that class

(Then, mayve we need a map to store books (orderbook obj) by bookID) -> Orders stored by orderId


Add / Delete

1. Look up map of orderbooks -> find orderbook object
2. In orderbook object -> look up map for orderId, If found/not-found -> make change to that entry in map accordingly



XML Format
<AddOrder book="book-2", operations="SELL" price="101.00" volume="87" orderId="9663">

XML data -> struct (golang or for python, a dictionary)
struct order{
    type string `json:"type"`,
    bookName `json;"book"`,
    operatoins
    price
    ...
}

Add order -> add order to buy/sell a book

Delete order -> delete a previously existing order, if present


Add timestamps at the end (for calc,) create fields in the beginning



`OrderBook`

1st lets implement , classes maps and structs, add delete methods
