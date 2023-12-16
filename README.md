<div align="center">
  
# Metamorphic RocksDB
_External Compaction of LSM Storage with Parquet Generation for Hybrid Workloads_

</div>

For CS 839 Cloud-Native Database Systems by Michael Noguera, James Sorenson, and Geoffrey Xue

TODO: Link paper here

## Description

TODO: Image of compaction here

## Code and Data
There are several components to this project, which all can be found in this organization. Below is a breakdown of the repositories:

# 

[primary]() - LINK TODO - The primary Node RocksDB client. TODO more explanation

[metarocks-primary](https://github.com/Metamorphic-RocksDB/metarocks/tree/external-compaction) - The modified version of RocksDB that the Primary Node runs on. Sends out compaction requests and receives compaction complete responses

 #

[compactor](https://github.com/Metamorphic-RocksDB/remote-compactor) - The Compaction Node RocksDB client. Listens for compaction messages on the queue and performs them

[metarocks-compactor](https://github.com/Metamorphic-RocksDB/metarocks/tree/compactor) - The modified version of RocksDB that the Compaction Node runs on. Includes parquet generation as part of compaction

[metarrow](https://github.com/Metamorphic-RocksDB/metaarrow) - A slightly modified version of Apache Arrow that undefines some macros in Arrow to ensure metarocks-compactor builds successfully
#

For data, we use the [Connecticut Real Estate Sales 2001-2020 GL dataset](https://data.ct.gov/Housing-and-Development/Real-Estate-Sales-2001-2020-GL/5mzw-sjtu/about_data), a JSON dataset with just about 1 million rows.

[data-loader]() - LINK TODO - Loads all of the data into primary instance

[duckdb-client](https://github.com/Metamorphic-RocksDB/metamorphic-duckdb-client) - The OLAP DuckDB client used to perform analytical queries against the S3 parquet files
