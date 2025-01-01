### dump.py - parse IAR .ddf/.sfr definitions into JSON data

### DialogSc144xxRegs.java - Ghidra script to create SFR definitions based on said JSON data

## How to use

1. Acquire JSON definitions, either:
  - generate some using dump.py
  - use existing ones provided in defs/
  - write your own? good luck?
2. Place the .java file somewhere Ghidra finds it
  - for this you might need to add your custom scripts directory from the script manager (look for a list icon in the top right)
2. Load your blob using Ghidra
3. From the script manager, run the DialogSc144xxRegs script and select the appropriate JSON file for your chip
4. Ghidra should now have created an SFR memory region with most of the registers in it
  - some defined registers are in other parts of memory (mostly DIP/DSP regions), which I have not implemented yet.
  - Refer to the 'mmap' key in the JSON and create them manually, then re-run the script. It should now add those registers as well
