# 🚀 FPGA-Based Limit Order Book

A high-performance, hardware-simulated order book modeled after modern exchange architecture — implemented in SystemVerilog.

## 📈 Features

- Supports ITCH-style `ADD`, `UPDATE`, `DELETE` messages
- Sorted bid/ask arrays (descending/ascending)
- Automatic compaction on delete
- Tracks best bid/ask price and quantity
- Fully testbenched with waveform inspection

## 📂 Project Structure
fpga-order-book/<br>
├── rtl/<br>
│   └── order_book.sv<br>
│   └── parser_defs.sv<br>
├── sim/<br>
│   └── order_book_tb.sv<br>
├── waveforms/<br>
│   └── order_book_best_bid_ask.png<br>
├── README.md<br>
└── .gitignore<br>

## 📊 Sample Waveform

![Waveform](waveforms/order_book_best_bid_ask.png)

## 💬 tcl-console output

------ BID SIDE ------ <br>
BID[0] ID:11111111 P:1000 Q:10 <br>
------ ASK SIDE ------ <br>
Best Bid: $0 (0 shares) <br>
Best Ask: $0 (0 shares) <br>
---------------------- <br>
 <br>
------ BID SIDE ------ <br>
BID[0] ID:22222222 P:1050 Q:5 <br>
BID[1] ID:11111111 P:1000 Q:10 <br>
------ ASK SIDE ------ <br>
Best Bid: $1000 (10 shares) <br>
Best Ask: $0 (0 shares) <br>
---------------------- <br>
 <br>
------ BID SIDE ------ <br>
BID[0] ID:22222222 P:1050 Q:5 <br>
BID[1] ID:11111111 P:1000 Q:10 <br>
BID[2] ID:33333333 P:990 Q:20 <br>
------ ASK SIDE ------ <br>
Best Bid: $1050 (5 shares) <br>
Best Ask: $0 (0 shares) <br>
---------------------- <br>
 <br>
------ BID SIDE ------ <br>
BID[0] ID:22222222 P:1050 Q:5 <br>
BID[1] ID:11111111 P:1000 Q:10 <br>
BID[2] ID:33333333 P:990 Q:20 <br>
------ ASK SIDE ------ <br>
ASK[0] ID:aaaaaaaa P:1100 Q:15 <br>
Best Bid: $1050 (5 shares) <br>
Best Ask: $0 (0 shares) <br>
---------------------- <br>
 <br>
------ BID SIDE ------ <br>
BID[0] ID:22222222 P:1050 Q:5 <br>
BID[1] ID:11111111 P:1000 Q:10 <br>
BID[2] ID:33333333 P:990 Q:20 <br>
------ ASK SIDE ------ <br>
ASK[0] ID:bbbbbbbb P:1080 Q:10 <br>
ASK[1] ID:aaaaaaaa P:1100 Q:15 <br>
Best Bid: $1050 (5 shares) <br>
Best Ask: $1100 (15 shares) <br>
---------------------- <br>
 <br>
------ BID SIDE ------ <br>
BID[0] ID:22222222 P:1050 Q:5 <br>
BID[1] ID:11111111 P:1000 Q:10 <br>
BID[2] ID:33333333 P:990 Q:20 <br>
------ ASK SIDE ------ <br>
ASK[0] ID:bbbbbbbb P:1080 Q:10 <br>
ASK[1] ID:aaaaaaaa P:1100 Q:15 <br>
ASK[2] ID:cccccccc P:1150 Q:5 <br>
Best Bid: $1050 (5 shares) <br>
Best Ask: $1080 (10 shares) <br>
---------------------- <br>
 <br>
------ BID SIDE ------ <br>
BID[0] ID:22222222 P:1050 Q:5 <br>
BID[1] ID:11111111 P:1000 Q:999 <br>
BID[2] ID:33333333 P:990 Q:20 <br>
------ ASK SIDE ------ <br>
ASK[0] ID:bbbbbbbb P:1080 Q:10 <br>
ASK[1] ID:aaaaaaaa P:1100 Q:15 <br>
ASK[2] ID:cccccccc P:1150 Q:5 <br>
Best Bid: $1050 (5 shares) <br>
Best Ask: $1080 (10 shares) <br>
---------------------- <br>
 <br>
------ BID SIDE ------ <br>
BID[0] ID:22222222 P:1050 Q:5 <br>
BID[1] ID:11111111 P:1000 Q:999 <br>
BID[2] ID:33333333 P:990 Q:20 <br>
------ ASK SIDE ------ <br>
ASK[0] ID:bbbbbbbb P:1075 Q:11 <br>
ASK[1] ID:aaaaaaaa P:1100 Q:15 <br>
ASK[2] ID:cccccccc P:1150 Q:5 <br>
Best Bid: $1050 (5 shares) <br>
Best Ask: $1080 (10 shares) <br>
---------------------- <br>
 <br>
------ BID SIDE ------ <br>
BID[0] ID:22222222 P:1050 Q:5 <br>
BID[1] ID:33333333 P:990 Q:20 <br>
------ ASK SIDE ------ <br>
ASK[0] ID:bbbbbbbb P:1075 Q:11 <br>
ASK[1] ID:aaaaaaaa P:1100 Q:15 <br>
ASK[2] ID:cccccccc P:1150 Q:5 <br>
Best Bid: $1050 (5 shares) <br>
Best Ask: $1075 (11 shares) <br>
---------------------- <br>
 <br>
------ BID SIDE ------ <br>
BID[0] ID:22222222 P:1050 Q:5 <br>
BID[1] ID:33333333 P:990 Q:20 <br>
------ ASK SIDE ------ <br>
ASK[0] ID:aaaaaaaa P:1100 Q:15 <br>
ASK[1] ID:cccccccc P:1150 Q:5 <br>
Best Bid: $1050 (5 shares) <br>
Best Ask: $1075 (11 shares) <br>
---------------------- <br>
 <br>
Testbench complete. <br>
