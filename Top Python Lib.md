# Top Python Libraries — Data Engineering Only


## Core Data Processing

1. pandas — data manipulation, joins, cleaning
2. numpy — numerical computing, arrays
3. polars — fast pandas alternative
4. dask — parallel dataframe processing
5. pyspark — distributed big data processing

## File Formats / Storage

6. pyarrow — parquet & arrow format
7. fastparquet — parquet engine
8. fsspec — unified file system (S3, ADLS, GCS)

## Database / SQL

9. sqlalchemy — database connections
10. psycopg2 — PostgreSQL connector
11. pymysql — MySQL connector
12. duckdb — analytics SQL on files/dataframes

## Pipeline / Orchestration

13. airflow — workflow orchestration
14. prefect — modern orchestration
15. luigi — pipeline dependency manager

## API / Data Ingestion

16. requests — REST API ingestion
17. aiohttp — async ingestion

## File System / OS

18. os — system operations
19. pathlib — modern file handling

## Data Quality / Utilities

20. great_expectations — data validation

# Typical Data Engineering Import Block

import os
from pathlib import Path

import pandas as pd
import numpy as np
import polars as pl
import dask.dataframe as dd

import pyarrow as pa
import duckdb

from sqlalchemy import create_engine
import psycopg2

import requests
