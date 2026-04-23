# 📡 5G Network Slicing Simulator

> A discrete-event simulation framework for exploring dynamic resource allocation across 5G network slices — built with Python & SimPy.

---

## 📋 Table of Contents

- [Project Description](#-project-description)
- [System Requirements](#-system-requirements)
- [Installation & Setup](#-installation--setup)
- [How to Run](#-how-to-run-the-project)
- [Viewing Results](#-viewing-results)
- [Complete Execution Workflow](#-complete-execution-workflow)
- [Project Structure](#-project-structure)
- [Understanding the Scenarios](#-understanding-the-scenarios)
- [Configuration Customization](#-configuration-customization)
- [Interpreting Results](#-interpreting-results)
- [Troubleshooting](#-troubleshooting)
- [Additional Notes](#-additional-notes)

---

## 📖 Project Description

This project is a **5G Network Slicing Simulator** built with Python and SimPy. It simulates different network slicing scenarios to compare how network resources are allocated and managed across different slicing strategies:

| Scenario | Description |
|----------|-------------|
| 🟢 **Normal** | Standard resource allocation |
| 🔵 **Improved** | Optimized resource allocation strategy |
| 🔴 **Congested** | High load scenario to test under stress |

The simulator generates detailed statistics and visualization plots showing network performance metrics under different slicing configurations.

---

## 💻 System Requirements

| Requirement | Details |
|-------------|---------|
| **Python** | 3.7 or higher |
| **Package Manager** | pip |
| **OS** | Linux, macOS, or Windows with terminal/command prompt |

---

## ⚙️ Installation & Setup

### 1. Navigate to the Project Directory

```bash
cd /home/shreyash/5G-Network-Slicing
```

### 2. Install All Required Dependencies

```bash
pip install -r requirements.txt
```

**Main dependencies include:**

| Package | Purpose |
|---------|---------|
| `simpy` | Discrete event simulation framework |
| `numpy` | Numerical computations |
| `matplotlib` | Data visualization and plotting |
| `PyYAML` | Configuration file parsing |
| `scikit-learn` | Machine learning utilities |
| `scipy` | Scientific computing |

---

## ▶️ How to Run the Project

The project provides **three different network slicing scenarios**:

### 🟢 Normal Scenario — Standard Configuration

```bash
python -m slicesim slicesim/normal.yml
```

Runs the simulator with standard resource allocation.  
📁 **Output:** `Outputs/normal.png`

---

### 🔵 Improved Scenario — Optimized Configuration

```bash
python -m slicesim slicesim/improved.yml
```

Runs the simulator with improved/optimized resource allocation strategy.  
📁 **Output:** `Outputs/improved.png`

---

### 🔴 Congested Scenario — High Load Configuration

```bash
python -m slicesim slicesim/congested.yml
```

Runs the simulator under congested/stress conditions.  
📁 **Output:** `Outputs/congested.png`

---

## 📊 Viewing Results

After running any simulation, the following outputs are generated:

### Output Files

| File | Description |
|------|-------------|
| `normal.png` | Performance under normal conditions |
| `improved.png` | Performance with improved allocation strategy |
| `congested.png` | Performance under high load |
| `output.txt` | Detailed simulation statistics and logs |

> 📂 All PNG files are automatically saved in the `Outputs/` directory.

### Viewing the Plots

**Linux:**
```bash
display Outputs/normal.png
display Outputs/improved.png
display Outputs/congested.png
# or
xdg-open Outputs/normal.png
```

**macOS:**
```bash
open Outputs/normal.png
```

**Windows:**  
Double-click the PNG files in the `Outputs/` folder.

---

## 🔄 Complete Execution Workflow

Follow these steps to run all scenarios and generate all comparison plots:

```bash
# Step 1: Navigate to project directory
cd /home/shreyash/5G-Network-Slicing

# Step 2: Run Normal scenario
python -m slicesim slicesim/normal.yml
# (Wait for execution to complete)

# Step 3: Run Improved scenario
python -m slicesim slicesim/improved.yml
# (Wait for execution to complete)

# Step 4: Run Congested scenario
python -m slicesim slicesim/congested.yml
# (Wait for execution to complete)
```

**Step 5:** Navigate to the `Outputs/` folder and open:
- `normal.png`
- `improved.png`
- `congested.png`

**Step 6:** Open `output.txt` to see detailed numerical results and logs.

---

## 🗂️ Project Structure

```
5G-Network-Slicing/
├── README.txt                      # This file
├── requirements.txt                # Python dependencies
├── Outputs/                        # Generated output files
│   ├── output.txt                  # Simulation logs and statistics
│   ├── output.png                  # Sample output image
│   └── output_n5000_t3600.png      # Sample output image
└── slicesim/                       # Main simulator package
    ├── __init__.py                 # Package initialization
    ├── __main__.py                 # Entry point for execution
    ├── normal.yml                  # Normal scenario configuration
    ├── improved.yml                # Improved scenario configuration
    ├── congested.yml               # Congested scenario configuration
    ├── BaseStation.py              # Base station simulation module
    ├── Client.py                   # Client/UE simulation module
    ├── Container.py                # Container/resource management
    ├── Coverage.py                 # Coverage area calculations
    ├── Distributor.py              # Traffic distribution module
    ├── Graph.py                    # Graph data structure
    ├── Slice.py                    # Network slice implementation
    ├── Stats.py                    # Statistics collection and analysis
    └── utils.py                    # Utility functions
```

---

## 🔬 Understanding the Scenarios

### 🟢 Normal Scenario (`normal.yml`)

- Uses basic network slicing configuration
- Standard resource allocation strategy
- Suitable **baseline** for comparison
- Output shows typical performance metrics

### 🔵 Improved Scenario (`improved.yml`)

- Implements **optimized** resource allocation
- Better load balancing across network slices
- Should show improved performance compared to normal scenario
- Demonstrates advanced slicing strategies

### 🔴 Congested Scenario (`congested.yml`)

- High number of clients/devices on the network
- **Heavy traffic load**
- Tests network performance under stress
- Shows system behavior when resources are constrained

---

## 🛠️ Configuration Customization

To modify simulation parameters, edit the YAML configuration files:

```
slicesim/normal.yml
slicesim/improved.yml
slicesim/congested.yml
```

**Common parameters you can modify:**

| Parameter | Description |
|-----------|-------------|
| `simulation_time` | Duration of simulation (in seconds) |
| `num_clients` | Number of clients/UEs in the simulation |
| `limit_closest_base_stations` | Maximum base stations per client |
| `delay_tolerance` | QoS delay requirements |
| `bandwidth_guaranteed` | Guaranteed bandwidth per slice |
| `plotting_params` | Output visualization settings |

---

## 📈 Interpreting Results

The generated plots typically show:

- 📶 Network resource utilization
- ⏱️ Latency/delay metrics
- 🚀 Throughput statistics
- 🔀 Slice performance comparison
- 📡 Base station load distribution
- 👥 Client connection patterns

**Compare the three scenario plots to understand:**

1. How network slicing affects performance
2. Improvement gains of optimized strategies
3. Network behavior under congestion
4. Trade-offs between different configurations

---

## 🔧 Troubleshooting

<details>
<summary><strong>❌ ModuleNotFoundError: No module named 'simpy' (or similar)</strong></summary>

**Solution:** Install dependencies with:
```bash
pip install -r requirements.txt
```
</details>

<details>
<summary><strong>❌ "File Not Found" error when running simulation</strong></summary>

**Solution:** Make sure you're in the correct directory and using the exact file names.
</details>

<details>
<summary><strong>❌ Plots are not displayed automatically</strong></summary>

**Solution:** Manually navigate to `Outputs/` folder and open the PNG files.
</details>

<details>
<summary><strong>⚠️ Slow simulation execution</strong></summary>

**Note:** This is normal — simulations may take a few seconds to complete depending on your system specifications and simulation parameters.
</details>

---

## 📝 Additional Notes

- Simulations use **Discrete Event Simulation (DES)** framework
- Results are **stochastic** — multiple runs may show variations
- To see changes in results, modify configuration files or random seed
- For large simulations (many clients, long time), execution may take longer
- All output images are **high resolution (1000 DPI)** for clarity

---

## ❓ For Questions or Issues

1. Review the simulator source code in `slicesim/` directory
2. Check simulation logs in `output.txt` for detailed information
3. Verify all dependencies are correctly installed
4. Ensure YAML configuration files have correct syntax

---

<div align="center">

**5G Network Slicing Simulator** • Built with Python & SimPy

</div>
