# Systems Project

In this project, you will be designing and a TSDB similar to Prometheus. We provide you
with stencil code written in Rust.

## Data Model

Each entry or sample in the database takes the following form:

```
series-name <label-key=label-value,...> <metric-name=metric-value,...> timestamp
```

The components are as follows:

* `series-name`: The name of the series. This is akin to a table in an RDBMS. Each
series is comprised of a fixed set of metrics (akin to columns in the RDBMS).
* `label-key` and `label-value`: These are key-value pairs that identify the context of
this sample. For example, metrics for CPU utilization might be identified by the region
and machine ID (e.g. `region=US-West, machine-id=1`).
* `metric-name` and `metric-value`: These are the the numeric values in the timeseries.
These are similar to columns in an RDBMS. Unlike Prometheus, a `series` can be
multivariate. This is a sensible data modeling decision especially for series that are
naturally multivariate like giroscopes (e.g. x, y, z, and error axes).
* `timestamp`: This the timestamp when this entry was sampled.

A simple way to think about this is that a series is a table where one column is the
timestamp, and the remaining columns are the metrics. Labels are then external metadata
that point a user to a particular row in that table. They aren't columns in the table
because an entry in the series could have a very different set of labels from another
entry in the series.

## Code and Architecture

### Repositories

[https://github.com/fsolleza/timeseries-storage](https://github.com/fsolleza/timeseries-storage)
contains the code that you will be editing. You'll need to install Rust for this to work.
Feel free to use Rust Nightly if you need features or are using a Crate depend on features
not available in Stable.

[https://github.com/fsolleza/tsbs](https://github.com/fsolleza/tsbs) contains a fork of
the [Time Series Benchmark Suite](https://github.com/timescale/tsbs). This version makes
two big modifications:

1. It fixes a bug in the code associated with random-walk distributions "maxing out"
2. It adds a high-cardinality `ip-address` label, and churn to the data sources in the
   `devops` workload.

### High Level Architecture

The high level architecture of the code is below.

TBD

The architecture follows a client-server architecture. It uses a TCP Socket to communicate
between clients and the server. This communication is done using `String`s. Specifically,
operations are sent from the client to the server in JSON format.


### Client

The client is a simple read-eval-print-loop (REPL) that reads from `stdin`. You can pipe
operations into the client or type the into the terminal. Apologies that it doesn't look
pretty. `Ctrl-c` exits the client. The client then sends the `String` to the server over a
TCP stream.

### Server

The server receives bytes over the TCP stream which it subsequently converts to a
`String`. It then uses the `serde` crate to try to deserialize this `String` to one of the
supported operations. If it successfully does so, it `execute`s that operation. Otherwise,
it responds to the client with an error.

The `execute` function handles this execution and can return a series resulting from the
requested operation. If so, the server `postprocess`es the series to convert it to a
`String` that it can send back to the client.

### Operations

The system currently only supports two operations: `write` and `select`. The `write`
operation simply writes an entry into the database.

The `select` operation takes a series name and a predicate. The predicate can be:
* `label-key` and `label-value` pair (e.g. `region=US-west`)
* a `metric-name` and `metric-value` (e.g. `queue-length > 0`)
* or a timestamp (e.g. `timestamp <= <some-timestamp>`)

The system supports `=, <, >, <=, >=` comparisons. Predicates are combined using `And` or
`Or`.

[return home][index.md]
