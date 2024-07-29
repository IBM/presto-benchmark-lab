---
title: Introduction
description: The description for the social card
logo: images/ibm-blue-background.png
---

# Introduction

## Presto Workshop - Deploying Presto C++ and Benchmarking with pbench

Welcome to our Presto C++ workshop! This workshop will provide an overview of Presto C++, the next-gen native Presto worker.
You will learn how to deploy Presto C++ with Docker Compose on your machine and set up a local file-based data source. We will then demonstrate how to run queries manually with Presto CLI and run the new-open source benchmarking tool
[pbench](https://github.com/prestodb/pbench). Then, you will deploy a similar Presto Java cluster to compare
the execution time with Presto C++ on a TPC-DS benchmark.

By the end of the workshop, you will know

- What Presto C++ is and its benefits
- How to set up and deploy Presto C++ with Docker Compose locally
- How to use the Presto CLI to run queries
- How to use pbench to run benchmarks and view results
- How to get a quantified speed-up factor of Presto C++ vs Java

### About this workshop

The introductory page of the workshop is broken down into the following sections:

* [Agenda](./#agenda)
* [Compatibility](./#compatibility)
* [Technology Used](./#technology-used)
* [Credits](./#credits)

## Agenda

|                                                     |                                                      |
|:----------------------------------------------------|:-----------------------------------------------------|
| [Part 1](deploy-presto/README.md) | Set-up and deployment of Presto C++ and Java locally |
| [Part 2](running-pbench/README.md)  | Downloading and running pbench                       |

## Compatibility

This workshop has been tested on the following platforms:

* **MacOS**: Apple Silicon (M-series chips)

## Technology Used

* Docker: A container engine to run several applications in self-contained containers
* Docker Compose: A YAML-based tool for defining and running multi-container applications
* Presto: Fast and Reliable SQL Engine for Data Analytics and the Open Lakehouse
* pbench: A new, open-source benchmarking tool for Presto

## Credits

* [Pramod Satya](https://github.com/pramodsatya)
* [Andrew Xie](https://github.com/Archy-X)
* [Allen Shen](https://github.com/allenshen13)
