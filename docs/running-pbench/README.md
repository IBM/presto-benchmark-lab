# Running pbench

At this point, you should already have a Presto C++ or Presto Java cluster with Docker Compose
running.

## 1. Download pbench

### 1.1 Download the pbench tar

Download the pbench tar for your platform below. This contains the compiled pbench
binary and the relevant benchmark configuration files.

- [MacOS (ARM)](https://presto-virtual-lab.s3.amazonaws.com/pbench_darwin_arm64.tar.gz)
- [MacOS (x86)](https://presto-virtual-lab.s3.amazonaws.com/pbench_darwin_amd64.tar.gz)
- [Linux (x86)](https://presto-virtual-lab.s3.amazonaws.com/pbench_linux_amd64.tar.gz)
- [Linux (ARM)](https://presto-virtual-lab.s3.amazonaws.com/pbench_linux_arm64.tar.gz)

### 1.2 Extract pbench

Extract the downloaded tar.gz file and change into the created `pbench` directory in a
new terminal window.

```bash
cd pbench
```

## 2. Run pbench

Once in the `pbench` directory, run pbench with `./pbench run` and specify the benchmark configuration files
related to the run. This example uses the sf1 scale factor and ds_power run flavor, which runs all 99 TPC-DS queries
sequentially.

For Presto C++:

```bash
./pbench run benchmarks/native_oss.json benchmarks/tpc-ds/sf1.json benchmarks/tpc-ds/ds_power.json
```

For Presto Java:
```bash
./pbench run benchmarks/java_oss.json benchmarks/tpc-ds/sf1.json benchmarks/tpc-ds/ds_power.json
```

You should see logs for each query being submitted and the results, including execution time and row count.

Supplying different json files allow you to run different benchmarks. For more information on this format, visit
the [pbench wiki](https://github.com/prestodb/pbench/wiki/Configuring-PBench).

### Troubleshooting

If you see a permissions pop-up that prevents running pbench on MacOS, run the following command on the
downloaded .tar.gz file before extracting:

```bash
xattr -d com.apple.quarantine pbench_darwin_arm64.tar.gz
```
Change this command depending on the pbench file you downloaded.
