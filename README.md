# Simple In-Memory Trading Engine

A simplified, single-threaded, in-memory trading engine implemented in **C++**.  
It features a basic **limit order book** and supports **limit order submissions** and **cancellations**.

---

## Features

- Limit Order Support – Submit limit orders to the engine  
- Order Cancellation – Cancel existing orders  
- In-Memory Design – All order book data stored in memory for high performance  
- Basic Matching Algorithm – Matches orders based on price–time priority  

---

## Project Structure

- **Engine.h** – Core of the engine, manages order books, orders, cancellations, and trade execution  
- **OrderBook.h** – Manages buy/sell sides of the market and handles matching logic  
- **PriceLevel.h** – Collection of orders at a specific price (FIFO order handling)  
- **Order.h** – Data structure for trade orders (quantity, price, side)  
- **OrderIndex.h** – Maps `orderId` to its location in the book (for fast lookups/cancellations)  
- **NumberUtil.h** – Bitwise utilities for encoding/decoding order locations  
- **EngineConstants.h** – Defines constants (e.g., max price levels, max orders)  
- **IEngine.h** – Interface defining core engine functionalities (`limit` and `cancel`)  
- **PriceLevelComparator.h** – Logic for comparing `PriceLevel` objects  
- **Side.h** – Enumeration for trade sides (`BUY` and `SELL`)  
- **Trade.h** – Data structure for completed trades (order IDs, quantity, price)  

Additional files:  
- **main.cpp** – Demonstration of engine functionality  
- **Engine** / **main** – Compiled executables  
- **.dSYM** – Debugging symbols (useful for crash analysis)

---

## How to Compile and Run

1. Save all files (`Engine.h`, `OrderBook.h`, `Order.h`, etc.) in the same directory.  
2. Compile using `g++`:

   ```bash
   g++ -std=c++11 main.cpp -o trading_engine
3. Run the executable:

   ```bash
   ./trading_engine
   
---

Demo Walkthrough
The runDemo() function in Engine.h showcases the core engine features:
- **Initial Orders** – Submits several buy and sell orders
- **Order Book Snapshot** – Prints current state of the book
- **Cancellations** – Cancels orders and updates the snapshot
- **New Orders & Matching** – Adds new orders, triggering trades if matched
- **Final State** – Displays the final order book

---


Future Improvements
-Support for market orders
-Persistence (save order book state to disk)
-Multi-threading for concurrent order handling
-Extended trade reporting and analytics

---


License

This project is open-source. Feel free to modify and use it as needed.
