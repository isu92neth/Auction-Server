# Auction-Server
Implemented a server which can be used by clients to bid for items in a stock exchange.

## STOCK EXCHANGE - AUCTION SERVER Software V1.0
========================================
### ++ special features ++   
==================
+ CLIENT GUI
+ USER SESSION CONTROL
==================

### GROUP 01
--------

E/16/012 - A.M.I.N. Adikari
E/16/022 - D.L.C. Amarasinghe
E/16/025 - K.T.D. Amasith

Date : 30-06-2020


* To compile the programme
	javac Server.java

* To run the Server
	java Server


This command opens up 'ServerGui' user interface for AUCTION SERVER GUI.


#### AUCTION SERVER GUI
------------------

* The GUI initially displays stock items (Symbol, name) together with the current price of Symbols named FB, VRTU, MSFT, GOOGL, YHOO, XLNX, TSLA and TXN. 
  These stock data appears with updates happening for each 500ms and displays real time.

* All the offers given by the clients through 'ClientGui' and the price changes done through the 'ServerGui' are displayed in a table with 'Client Name', 'Symbol', 'Price', 'Date', 'Time' in real time.

** This GUI contains three buttons

1. CHANGE PRICE
2. SHOW STOCK
3. SHOW

1. * Clicking 'CHANGE PRICE' button pops up 'ChangePriceGui' GUI.
   * Server user can search for a symbol using Search Bar and click 'SEARCH'
   * If such symbol exists in the stock, GUI displays security name and its current price, if not it displays an error message.
   * After entering new price value, corresponding stock can be updated with new price by clicking 'CHANGE' button.
   * The deatils of the change done to the stock is displayed in the table on 'ServerGui'.

2. * Clicking 'SHOW STOCK' button pops up 'StockListGui' GUI.
   * It displays all the details ('SYMBOL', 'SECURITY NAME', 'PRICE') of all the stocks.
   
3. * Server user can view price changes (BID HISTORY) of a particular stock.
   * User can search for a symbol using Search Bar and click 'SHOW'
   * Clicking 'SHOW' button pops up 'BidHistoryGui' GUI with price changes (BID HISTORY) of the searched stock.



#### CLIENT GUI
----------

* Client can connect to the server using communication tool 'nc' in linux terminal.

* When the server is working, to connect the server
	nc <Host_Name> 2000
	
	<Host_Name> = IP address of the host where server is situated

* This command opens up 'ClientGui' user interface for CLIENT GUI.

* Client should click 'START BID' button to start the process.

* Once a client enters a 'Name' and click 'NEXT' button twice to allows user to enter a 'Symbol'.

  NOTE : User should click 'NEXT' button "Twice" in order to verify name of the client.

** We have Created user session to TRACK users who actively bidding with Server. So Same names cannot
   use for same time in server to bidding.  

* Then, with a valid 'Symbol', click 'NEXT' button shows 'Security Name' and 'Current Price' of the stock.
  Client can enter a 'Bid Price'.
  If 'Input Price' is greater than 'Current Price' of the stock, user can confirm the procedure using 'CONFIRM'   button.
  Otherwise, client will get a warning to enter a 'Price'
  Client should input a 'Price' value greater than 'Current Price' of the stock, in order to confirm the procedure.

* Client can enter more greater bid values for previously enterd Symbol in one session.
   (+ One bid session for one sequrityname+)

* Clicking 'QUIT' button, terminate the bidding procedure.

* A client can bid again with the same name.
