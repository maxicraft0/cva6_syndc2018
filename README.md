# cva6_syndc2018
The repositary contains the edited systemverilog code of cva6 that is synthesizable by design-compiler 2018

CVA6 is a opensource riscv project maintained by openhwgroup.
Since synopsys DC does not support some of the features of recent systemverilog codes,
cva6 is not directly synthesizable by DC. In this repo we made some changes to the original cva6 HDL codes, including:

- macro definitions: DC 2018 does not support default value for macro definitions.
- macro definitions: DC 2018 requires a explicit '\' for newline in macro definition. 
- structure array: DC 2018 does not support structure array range selection. So convert to primitive type array first.
- Width mismatch: DC 2018 reports error during linking when port with mismatch for a module.

Just replace the problematic HDL source file with our edited ones will work fine for DC.
Or use our pre-written tcl script to analyze the HDL of cva6:
```
source read_sv.tcl
```
After analyze, you can run elaborate/link to check any errors.

