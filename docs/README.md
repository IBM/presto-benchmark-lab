---
title: Introduction
description: The description for the social card
logo: images/ibm-blue-background.png
---

# Presto C++ Workshop

## Deploying Presto C++ and Benchmarking with pbench

Welcome to our Presto C++ workshop! This workshop will provide an overview of Presto C++, the next-gen Presto worker.
You will learn how to deploy Presto C++ with Docker Compose on your machine and query TPC-H, TPC-DS data from your
local file-system with the Hive and Iceberg connectors (using file-based hive metastore). We will then demonstrate how
to run queries manually with Presto CLI and look at how the open source benchmarking tool [pbench](https://github.com/prestodb/pbench) can be used
to run TPC-DS benchmarks against your Presto cluster. We will use pbench to compare the performance of Presto and Presto
C++ on the TPC-DS benchmark.

By the end of the workshop, you will know

- What Presto C++ is and its benefits
- How to set up and deploy Presto C++ with Docker Compose locally
- How to use the Presto CLI to run queries
- How to use pbench to run benchmarks and view results
- How to get a quantified speed-up factor of Presto C++ vs Java

This workshop is organized into the following sections:

* [Agenda](./#agenda)
* [Compatibility](./#compatibility)
* [Technology Used](./#technology-used)
* [Credits](./#credits)

## Agenda

|                                                     |                                                      |
|:----------------------------------------------------|:-----------------------------------------------------|
| [Part 1](deploy-presto/README.md)  | Set-up and deployment of Presto C++ and Presto Java locally |
| [Part 2](running-pbench/README.md) | Downloading and running pbench                             |

## Compatibility

This workshop has been tested on the following platforms:

* **aarch64**: Apple Silicon (M-series chips)

## Technology Used

* Docker: A container engine to run several applications in self-contained containers
* Docker Compose: A YAML-based tool for defining and running multi-container applications
* Presto: Fast and Reliable SQL Engine for Data Analytics and the Open Lakehouse
* pbench: A new, open-source benchmarking tool for Presto

## Credits

* [Pramod Satya](https://github.com/pramodsatya)
* [Andrew Xie](https://github.com/Archy-X)
* [Allen Shen](https://github.com/allenshen13)
