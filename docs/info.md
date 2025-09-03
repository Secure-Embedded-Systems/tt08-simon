<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

This is a bitserial implementation of the SIMON Block Cipher. A
bit-serial implementation exchanges throughput for area, thereby
creating a compact cipher that is dominated by flip-flops and
multiplexer cells.  However, the overal design size becomes minimal. 
The design uses a 3-bit input and a 2-bit output, in addition to clock and reset.
The data input is asserted by the control word, and must be valid when
the control word indicates a plaintext-loading or key-loading
operation.
The data output is asserted by the valid bit, and should be ignored
when the data valid bit is 0. The output ciphertext is produced in 128
consecutive clock cycles.
The 2-bit control word defines the operation of the cipher. The LSB is
a debug bit study to key-loading process and to verify that the key
register was correctly loaded.

## LIMITATIONS

This design forces the key bits to 0 upon loading, so that the
effective key value of the cipher is always hardcoded to 0.
This disables the use of the design as a cipher, yet it still 
demonstrates how a bit-serial architecture can be designed.

## How to test

Study the testbench for example test vectors.

## External hardware

No external hardware is needed for this project.
