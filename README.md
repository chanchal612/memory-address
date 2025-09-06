# memory-address
#Hexadecimal Representation


1.Hexadecimal System (Base-16) uses 16 digits: 0–9 and A–F, where A = 10, B = 11, ..., F = 15.

2.Each hex digit equals 4 binary bits. For example: A = 1010, F = 1111.

3.Binary to Hex Conversion:
  -Group binary digits into sets of 4 from right to left.
  -Pad with zeros if needed and replace each group with its hex equivalent.

4.In C programming, hexadecimal numbers are written with a 0x prefix.

Example: int num = 0x1AD; represents a decimal value of 429.



#Memory Address Range

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
Segmentation in C and Operating System – Quick Notes

Segmentation in OS & C:

RAM of size 1 MB is divided into 16 equal parts (segments).

Each segment = 64 KB, and this process is called segmentation.

16
×
64
 KB
=
1
 MB
16×64 KB=1 MB

Memory Address Structure in Turbo C 3.0:

Physical memory address = 20-bit address.

But pointers in C are not 20-bit, so segmentation is used.

Address = Segment:Offset, where:

Segment number = 4 hex digits

Offset address = 4 hex digits

E.g., Address 0x500F1 → Segment: 0x5000, Offset: 0x00F1

Pointer Types in Turbo C 3.0:

To handle limited pointer size:

near pointer → accesses only current 64KB segment

far pointer → accesses full 1MB using segment:offset

huge pointer → like far, but can move across segments

Offset Address in C:

The offset is the position of a variable within a segment.

Ranges from 0x0000 to 0xFFFF.Data Segment in C – Quick Notes

Each memory segment has a specific purpose in Turbo C (DOS-based systems):

Example:

Segment 15 → ROM

Segment 14 → BIOS

Segment 8 → Special segment called Data Segment

Segment 8: Data Segment is crucial for C programming and is used to store:

Global variables

Static variables

Constants/data used during program execution

The Data Segment is divided into 4 parts (details usually discussed in low-level memory models or advanced chapters like pointers/unions in graphics programming).

Accessing special memory areas (like text/graphics video memory) is possible using pointers and unions, typically in graphics programming with 255-color modes (older DOS-style programming).Stack Area in C (Turbo C 3.0) – Quick Notes

Stack Area stores automatic variables and constants, including:

Local variables with default (auto) storage class

Function parameters and return values

Constants used in expressions (int, float, char, string)

Automatic variables are temporary:

Created when the block is entered

Destroyed when the block ends (out of scope)

Stack is also called the Temporary Memory Area

Stack follows LIFO (Last-In, First-Out) structure:

Last variable pushed is the first to be accessed

This affects the order in which values are read (especially when not explicitly referenced)

Initialized vs. Uninitialized Variables in Stack:

Initialized variables are stored closer (on top) in the stack

Uninitialized variables are stored further away

This affects the default output in Turbo C when variable names are omitted in printfData Area in C – Quick Notes

Data Area stores:

All static variables

All extern variables

It is a permanent memory area (unlike stack)

Variables in the data area are not destroyed after going out of scope — they retain their values throughout the program's execution.

This area is used when a variable needs to preserve its value between function calls or loops.

Static variables are initialized only once, and the value is updated (if modified) and retained in the next usage.Heap Area in C – Quick Notes

Heap Area is used for dynamic memory allocation at runtime.

Memory from the heap is manually managed by the programmer.

In C, memory is allocated in the heap using functions like:

malloc() – allocates uninitialized memory

calloc() – allocates and initializes memory to zero

The size of the heap area is not fixed — it depends on the available free memory in the system at runtime.

Memory allocated in the heap persists until it is manually freed using free() — unlike stack or data area, the lifetime is programmer-controlled.Code Area in C – Quick Notes

Code Area (also called text segment) is the memory region where the compiled program instructions (code) are stored.

This area is typically read-only, to prevent accidental modification of program instructions during execution.

The size of the code area is fixed at the time of program loading and does not change during execution.

Function pointers can access and reference addresses in the code area, allowing dynamic function calls.Data Types in C – Quick Notes

C data types can be broadly classified into:

Integral types (whole numbers):

char — stores single characters (1 byte)

int — stores integers (typically 2 or 4 bytes)

Real (floating-point) types:

float — single precision decimal numbers

double — double precision decimal numbers

Void type:

void represents no data or nothing (used in functions for no return value or generic pointers).

Note:

Apart from these primitive/basic types, many other data types exist (like long, short, unsigned, structures, unions, enums, etc.) which are often defined in header files or advanced topics.
