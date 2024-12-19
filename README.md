# VeriVerse 2.0
## Makefile for iverilog
```makefile
# Variables
TOP_MODULE = your_module
VERILATOR_FILES = -o $(TOP_MODULE)_SYN $(TOP_MODULE).v $(TOP_MODULE)_tb.v

# all: clean compile simulate

compile: clean
	@echo "Running iverilog..."
	@iverilog $(VERILATOR_FILES)

run:
	@echo "Running simulation..."
	@./$(TOP_MODULE)_SYN

clean:
	@echo "Cleaning up..."
	rm -rf *.vcd $(TOP_MODULE)_SYN

wave:
  gtkwave dump.vcd
```

## Commands to run 
```bash
make compile && make run
```
## Commands to open the waveform 
```bash
make waveform
```
