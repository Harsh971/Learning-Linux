# Compression and DeCompression Command in Linux

## Description

**`gzip`**, **`bzip2`**, and **`xz`** are three popular compression utilities in Linux used to compress and decompress files and archives. They each use different compression algorithms and offer varying levels of compression and speed.

### 1. gzip :
**`gzip (GNU Zip)`** is a widely used compression utility that uses the DEFLATE compression algorithm. It's known for its fast compression and decompression speed and is commonly used for compressing individual files.
```
gzip  [options]  [file]
```
#### Examples:
```
gzip myfile.txt           # Compresses myfile.txt to myfile.txt.gz
gzip -d myfile.txt.gz     # Decompresses myfile.txt.gz to myfile.txt
```
### 2. bzip2 :
**`bzip2`** is a compression utility that uses the Burrows-Wheeler transform followed by Huffman coding. It provides better compression ratios than gzip but is generally slower.
```
bzip2  [options]  [file]
```
#### Examples:
```
bzip2 myfile.txt          # Compresses myfile.txt to myfile.txt.bz2
bzip2 -d myfile.txt.bz2   # Decompresses myfile.txt.bz2 to myfile.txt
```
### 3. XZ :
**`xz`** is a compression utility that uses the LZMA compression algorithm. It provides the highest compression ratio among the three utilities but is also the slowest.
```
xz  [options]  [file]
```
<br><img src="https://github.com/Harsh971/Learning-Linux/blob/main/Storage%20Management/gzip%20bzip2%20xz%20Commands/image1.png"><br><br>
#### Examples:
```
xz myfile.txt             # Compresses myfile.txt to myfile.txt.xz
xz -d myfile.txt.xz       # Decompresses myfile.txt.xz to myfile.txt
```

##Options:
- **-c, --stdout:** Write output to standard output instead of modifying the original file.
- **-d, --decompress:** Decompress the compressed file.
- **-f, --force:** Force compression or decompression even if the file already exists or the output file would overwrite an existing one.
- **-k, --keep:** Keep the original file after compression or decompression.
- **-v, --verbose:** Display verbose output.
- **-9:** Use the highest compression level (slower but produces smaller files).

## Comparison:
- **Compression Ratio:** `xz` provides the highest compression ratio, followed by `bzip2` and then `gzip`.
- **Compression Speed:** `gzip` is the fastest, followed by `bzip2` and then `xz`.
- **Decompression Speed:** `gzip` is generally the fastest for decompression, followed by `xz` and then `bzip2`.
- **Usage:** `gzip` is commonly used for fast compression of individual files, `bzip2` for better compression of individual files, and `xz` for maximum compression of large files or archives.