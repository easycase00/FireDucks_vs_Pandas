# FireDucks vs Pandas: A Benchmark Battle for Data Pipelines

This repository benchmarks **FireDucks**, a high-performance DataFrame library, against **pandas** in a real-world data pipelining scenario. The goal is to evaluate how FireDucks performs on large datasets compared to the conventional pandas library in terms of speed, memory usage, CPU efficiency, and scalability.

## Overview

When working with large datasets or building production ETL and machine learning pipelines, performance and resource efficiency are critical. FireDucks offers:

- Lazy execution: operations are deferred and batched.
- Batch optimization: multiple chained operations are compiled into a single efficient execution plan.
- Immutable DataFrames: promotes safe and scalable execution.
- Pandas-compatible API: minimal learning curve or migration cost.

## Benchmark Scenario

Both pandas and FireDucks were tested on the following pipeline:

1. Load a CSV file containing 5 million rows
2. Compute a derived column: `income_per_age`
3. Group by `gender` and calculate aggregates
4. Sort by `income`
5. Filter rows where `age > 30`

## Metrics Captured

- Execution Time (seconds)
- Memory Usage (MB)
- CPU Usage (%)
- Throughput (rows processed per second)
- Step-by-step timing (FireDucks only)

## Results

| Metric                  | Pandas             | FireDucks           | Verdict                                   |
|-------------------------|--------------------|----------------------|--------------------------------------------|
| Execution Time          | 19.61 sec          | 7.15 sec             | FireDucks is ~2.7× faster                  |
| Memory Usage            | 1189 MB            | 1423 MB              | Slightly higher due to lazy caching       |
| CPU Usage               | 2.50%              | 2.00%                | FireDucks uses ~20% less CPU              |
| Rows/sec Throughput     | 254,978 rows/sec   | 699,218 rows/sec     | FireDucks processes ~2.7× more rows/sec   |
| Operation Timing        | —                  | Near-zero post-read  | Efficient batched execution               |

## Visualization Snapshot

The result dashboard displays bar plots comparing time, memory, CPU usage, throughput, and step-wise FireDucks timings. FireDucks showed consistent gains in speed and throughput with only a minor memory tradeoff.

## Why Use FireDucks?

- Optimized execution: chained operations are compiled and optimized.
- Resource efficiency: uses less CPU and reduces infrastructure cost.
- Scalability: excellent throughput, even on massive datasets.
- Easy adoption: compatible with pandas API.

## Business Impact

- Reduced cloud costs due to lower CPU usage.
- Faster pipelines lead to real-time insights and quicker iteration.
- Future-proofed for scaling up data sizes and workflows.

## Conclusion

If you are hitting the limits of pandas in your pipelines, FireDucks provides a high-performance alternative with significant speedups and efficiency. It's a drop-in, smart upgrade to your pandas workflows.

## Requirements

- Python 3.8+
- pandas
- fireducks
- seaborn
- matplotlib
- memory-profiler
- psutil

### Install dependencies

```bash
pip install -r requirements.txt
