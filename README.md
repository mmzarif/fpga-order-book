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
│   └── screenshots/ (store annotated waveform images)<br>
├── README.md<br>
└── .gitignore<br>

## 📊 Sample Waveform

![Waveform](waveforms/screenshots/order_book_best_bid_ask.png)
