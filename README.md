# 🚀 FPGA-Based Limit Order Book

A high-performance, hardware-simulated order book modeled after modern exchange architecture — implemented in SystemVerilog.

## 📈 Features

- Supports ITCH-style `ADD`, `UPDATE`, `DELETE` messages
- Sorted bid/ask arrays (descending/ascending)
- Automatic compaction on delete
- Tracks best bid/ask price and quantity
- Fully testbenched with waveform inspection

## 📂 Project Structure
fpga-order-book/
├── rtl/
│   └── order_book.sv
│   └── parser_defs.sv
├── sim/
│   └── order_book_tb.sv
├── waveforms/
│   └── screenshots/ (store annotated waveform images)
├── README.md
└── .gitignore
