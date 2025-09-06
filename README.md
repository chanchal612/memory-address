# memory-address
Hexadecimal Representation


1.Hexadecimal System (Base-16) uses 16 digits: 0–9 and A–F, where A = 10, B = 11, ..., F = 15.

2.Each hex digit equals 4 binary bits. For example: A = 1010, F = 1111.

3.Binary to Hex Conversion:
  -Group binary digits into sets of 4 from right to left.
  -Pad with zeros if needed and replace each group with its hex equivalent.

4.In C programming, hexadecimal numbers are written with a 0x prefix.

Example: int num = 0x1AD; represents a decimal value of 429.



Memory Address Range

1.Address range depends on the number of address lines (bits).
   -For a 20-bit address bus:
      -Minimum address = 0x00000
      -Maximum address = 0xFFFFF

2.Total addressable memory = 2^20= 1 MB

3.Memory size conversions (common powers of 2):

2^10=1 KB

2^20=1 MB

2^30=1 GB

2^40=1 TB

Memory Cells and Data Storage

1.RAM is divided into equal parts called memory cells, and each cell stores 1 byte of data using the binary number system.



2.Each memory cell has a unique address in whole numbers, always in increasing order (e.g., 0x5000, 0x5001, 0x5002, ...).

3.Data types use different numbers of memory cells:

    -char (character) → 1 byte (1 cell)

    -int (integer) → 4 bytes (4 cells)

    -Stored in consecutive memory locations


Residence Memory & Physical Address 

1.Residence memory is the portion of RAM where a program is loaded during execution.

    -Example: Turbo C 3.0 uses 1 MB of residence memory when it runs.

2.All C variables are stored in the residence memory during program execution.

3.In Turbo C 3.0, the physical address (also called real address) is a 20-bit memory address.

4.With 20-bit addressing, the valid address range is:

    -0x00000 to 0xFFFFF (i.e., 1 MB total addressable space)

    -All C variables must be stored within this address range.
