

# Huffman Coding Implementation for Text Files in C++

This project implements **Huffman Coding**, a lossless data compression algorithm, to compress and decompress text files.

## Overview

Huffman Coding assigns variable-length codes to input characters, with shorter codes for more frequent characters, resulting in efficient compression.

## Features

- **Compression (Encoding):** Compresses input text files.
- **Decompression (Decoding):** Restores compressed files to their original form.

## Implementation Details

The project comprises:

- **`struct Node`:** Represents a node in the Huffman Tree, storing character data, frequency, Huffman code, and pointers to child nodes.
- **`class Huffman`:** Contains:
  - `compress()`: Compresses the input file.
  - `decompress()`: Decompresses the Huffman-encoded file.
  - Constructor: Initializes with input and output file names.

### Compression Process (`compress()`)

1. **`createMinHeap()`:** Reads the input file to determine character frequencies and constructs a Min Heap using a priority queue.
2. **`createTree()`:** Builds the Huffman Tree by combining nodes with the lowest frequencies iteratively.
3. **`createCodes()`:** Traverses the Huffman Tree to assign binary codes to each character.
4. **`saveEncodedFile()`:** Writes the encoded data to the output file in a specific format.

### Decompression Process (`decompress()`)

1. **`getTree()`:** Reconstructs the Huffman Tree from the encoded file's metadata.
2. **`saveDecodedFile()`:** Converts the binary encoded data back to the original text using the reconstructed tree.

## How to Run

### Prerequisites

- **C++ Compiler:** Ensure you have `g++` installed.

### Steps

1. **Clone the Repository:**
   ```sh
   git clone https://github.com/your-username/Huffman-Encoding.git
   cd Huffman-Encoding
   ```

2. **Compile the Encoder:**
   ```sh
   g++ -o encoder encode.cpp huffman.cpp
   ```

3. **Compress a File:**
   ```sh
   encoder inputFile.txt compressedFile.huf
   ```

4. **Compile the Decoder:**
   ```sh
   g++ -o decoder decode.cpp huffman.cpp
   ```

5. **Decompress a File:**
   ```sh
   decoder compressedFile.huf outputFile.txt
   ```

---
