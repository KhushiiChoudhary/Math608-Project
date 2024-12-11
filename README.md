# Comparing NumPy with Dask for Large-Scale Data Operations

This project demonstrates the differences between **NumPy** and **Dask** for handling large-scale data operations, focusing on performance, memory efficiency, and parallelism.

## Project Overview

### Objectives
- Compare the performance of NumPy and Dask in handling large arrays and dataframes.
- Illustrate Dask’s ability to work with datasets exceeding memory limits.
- Explore the use of Dask for parallelized computations, delayed execution, and efficient I/O operations.

### Key Features
1. **Large Array Creation**:
   - Created arrays of varying sizes with NumPy and Dask.
   - Demonstrated how Dask handles arrays larger than memory by chunking the data.

2. **Lazy Evaluation with `dask.delayed`**:
   - Built computation graphs for complex tasks without immediate execution.
   - Visualized the computation graphs to better understand task execution.

3. **Data Processing**:
   - Used both Pandas and Dask DataFrames to:
     - Read large CSV files.
     - Perform groupby and aggregation operations.
     - Merge and filter datasets.
     - Apply custom functions.
   - Compared performance metrics (time taken) for each operation.

## Setup Instructions

### Prerequisites
- Python 3.8+
- Installed libraries:
  - `numpy`
  - `pandas`
  - `dask`
  - `graphviz` (for visualizing computation graphs)

### Installation
1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```
2. Install the required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

3. Install Graphviz (if not already installed):
   ```bash
   # For Linux
   sudo apt-get install graphviz
   
   # For macOS
   brew install graphviz

   # For Windows
   choco install graphviz
   ```

4. Install Dask:
   ```bash
   pip install dask[complete]
   ```

   For more information, visit the [official Dask website](https://www.dask.org/).

### Running the Code
1. Open the Jupyter Notebook:
   ```bash
   jupyter lab
   ```
2. Navigate to `DaskProject.ipynb`.
3. Run the cells sequentially to see the outputs and comparisons.

## Results Summary

| **Operation**               | **Pandas Time**   | **Dask Time**     | **Speedup** |
|-----------------------------|-------------------|-------------------|-------------|
| Reading a CSV File          | 0.978 seconds    | 0.0029 seconds    | ~336x       |
| GroupBy and Aggregation     | 0.554 seconds    | 0.0086 seconds    | ~64x        |
| Merging Datasets            | 167.17 seconds   | 0.039 seconds     | ~4287x      |
| Filtering Data              | 0.023 seconds    | 0.005 seconds     | ~4.6x       |
| Applying Functions          | ~ (illustrative) | ~ (illustrative)  | (varies)    |

### Key Insights
- **Memory Efficiency**: Dask is designed to handle datasets that exceed available memory by partitioning the data into smaller chunks.
- **Parallelism**: Operations are parallelized in Dask, leading to significant speedups for large-scale operations.
- **Lazy Execution**: Dask delays computation until explicitly triggered, providing flexibility for optimizing workflows.

## Visualization
- Computation graphs were visualized using Dask's `.visualize()` method to showcase the workflow structure and dependencies.

## Future Work
- Extend comparisons to include operations like matrix multiplications and Fourier transforms.
- Integrate Dask with cloud-based storage solutions for distributed computing.



