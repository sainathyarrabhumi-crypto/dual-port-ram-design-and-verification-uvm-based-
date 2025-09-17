12x64 Parameterized SoC-Level Verification (UVM)
📌 Project Overview

This project implements a UVM-based verification environment for a 12x64 parameterized design at the SoC level. The environment instantiates 4 DUTs, verifies them individually and in parallel, and uses virtual sequences and sequencers for coordinated stimulus generation across multiple interfaces.

🛠️ Features

Design: 12x64 parameterized DUT (configurable width/depth)

Verification:

.UVM testbench architecture

.4 DUT instances verified in parallel

.Virtual sequencer to control multiple sequencers

.Virtual sequences for coordinated multi-DUT transactions

.Scoreboard with reference model for functional correctness

.Functional coverage collection

.SoC-Level Integration:

.Shared bus/interconnect support
.Stimulus across multiple DUTs simultaneously
.Stress and corner-case scenarios
├── rtl/
│   └── dut_12x64.v                # Parameterized 12x64 DUT
├── tb/
│   ├── top_tb.sv                  # Testbench top module
│   ├── env/                       # UVM environment
│   │   ├── soc_env.sv             # SoC-level environment
│   │   ├── soc_agent.sv           # Agent per DUT interface
│   │   ├── soc_seq_lib.sv         # Sequence library
│   │   ├── soc_virtual_seq.sv     # Virtual sequence for multi-DUT coordination
│   │   ├── soc_virtual_seqr.sv    # Virtual sequencer
│   │   ├── soc_monitor.sv         # Monitors for each DUT
│   │   ├── soc_scoreboard.sv      # Scoreboard with ref model
│   │   └── soc_coverage.sv        # Functional coverage
│   ├── tests/                     # UVM testcases
│   │   ├── base_test.sv
│   │   ├── directed_test.sv
│   │   └── random_test.sv
│   └── regression_list.txt        # List of tests for regression
├── waves/
│   └── simulation.vcd             # Sample waveform dump
└── README.md
📊 Verification Methodology

Stimulus:

Random & directed sequences

Coordinated operations across multiple DUTs using virtual sequences

Scoreboard:

Reference model to check correctness of all DUTs

Coverage:

Transactions across all DUTs

Interleaved access patterns

SoC-level corner cases (parallel reads/writes, conflicts, back-to-back transactions)

Regression Testing:

Multiple testcases run with different seeds

Coverage-driven closure

✅ Results

Verified all 4 DUTs under independent and coordinated operations

Ensured data integrity and transaction ordering across DUTs

Achieved 100% functional coverage at block + SoC level through regression




