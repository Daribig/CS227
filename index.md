# Everything is a Time Series

## What this class is about
Yes. Just as it's all just bits and bytes, it's all just time series also. This
class will be about modern Time Series Management Systems (TSMS) and the
current research around this area. It will focus on three topics that give you
an overview of the landscape:

1. Time Series Storage: We'll read about storage engines used in industry and
   and proposed in academia. The fundamental problems of time series storage:
   how to store so much data, how long to store the data, and how much of the
   data store? We'll learn about how different storage engines address the
   problem and compare their approaches, benefits, and drawbacks.

2. Time Series Similarity Search: Given some short time series, can we find the
   most similar segment(s) of a larger time series? We'll take a look at the
   algorithms and data structures that allow us to ask these questions. We'll
   identify different approaches to this problem and critique the current state
   of the art.

3. Streams and Modern Hardware: Before a time series is a time series, it's
   first a stream. Streams run the internet, your GPS device, and your bank
   account. We'll learn how industry deals with massive streams in their
   distributed infrastructure. We'll also contrast the current state of the art
   with what could be given considerations of modern hardware.

## Projects

You'll also be working on projects that involve modern or even novel techniques
to address a research question. We have our own ideas that we prefer you work on
or at least guide your project. We are also open to your own ideas.

### Project Requirements

* Significant coding portion that implements your research
* Must be written in Rust - We'll provide as much support as needed to get you
  up to speed
* A write up that describes what you did and how you did it, along with
  benchmarks or other measurements that you use to show whether your hypothesis
  was verified or not. (Not all "good" hypotheses are verified!)
* We'll have regular checkins:
    * Week of February 24: project idea
    * Week of March 15: progress check-in
    * Week of March 30: progress check-in
    * Week of April 13: progress check-in
    * Week of April 27: write-up check-in
* We'll have project presentations. We might have it on April 27, but it we'll
  definitely have it in the last day of class.

### Project Process

We stand on the shoulder of giants so we don't just go into it blindly. We'll
first implement something based on the current state of the art (SotA), and then
find its shortcomings. After implementing it or learning more about the
workloads that we expect we handle, we'll have some hypothesis of what workloads
the SotA excels and where it might not.

We then test our hypothesis by building a few experiments that show this to be
the case. Finally, we implement our ideas for how it could work better. It could
be a completely new structure, or an improvement on the current SotA
implementation.

### Project Ideas

**Storage**
* Implement BTrDB storage in Rust then compare with Gorilla or find
  optimizations to storage structure.
* Implement a Rust wrapper around TileDB and then explore how best to use TileDB
  as a time series storage structure

**Indexing**
* Investigate how to store and index time series tags in Gorilla or BTrDB. If in
  BTrDB, can be an optimization to the storage project.
* Implement some time series similarity search index - e.g. iSAX, Coconut, then
  how do you use this in multi-dimensional timeseries.

## Schedule

### Topic: Introduction to Time Series Management Systems (TSMS)

* **February 03**:
    * Introductions to the class
    * [InfluxDB's sell on TSDBs][2]
    * [Goku: Pinterest’s in-house time-series database (Video)][1]
    * [Spark ITS: Indexing for Large Scale Time Series Data on Apache Spark][20]

### Topic: Time Series Data and Storage

* **Febuary 10**: Storage in the wild
    * [Prometheus Storage Overview][3]
    * [Prometheus Storage Details][4]
* **Febuary 17**:
    * No class - President's Day
* **February 24**: Storage in the wild
    * [IndluxDB Storage][5]
    * [OpenTSDB Storage][6]
* **March 02**: Storage in papers
    * [Gorilla: A Fast, Scalable, In-Memory Time Series Database][7]
* **March 09**: Storage in papers 2
    * [BTrDB: Optimizing Storage System Design for Time Series Processing][8]

### Topic: Time Series Similarity Search

* **March 16**: Distance Measures
    * [Searching and Mining Trillions of Time Series Subsequences under Dynamic Time Warping][9]
* **March 23**: Spring break (helpful reads)
    * [iSAX: Indexing and Mining Terabyte Sized Time Series][10]
    * [SFA: A Symbolic Fourier Approximation and Index for Similarity Search in High Dimensional Datasets][11]
* **March 30**: Representation
    * [Coconut: A Scalable Bottom-Up Approach for Building Data Series Indexes][12]
* **April 06**: Clustering
    * [Multivariate Time Series Classification with WEASEL+MUSE][13]

### Topic: Massive Time Series

* **April 13**: Massive Streams (this is where the industry's at)
    * [Kafka: a Distributed Messaging System for Log Processing][14]
    * [Samza: Stateful Scalable Stream Processing at LinkedIn][15]
* **April 20**: Modern Hardware (this is what academia is concerned with)
    * [Analyzing Efficient Stream Processing on Modern Hardware][16]
    * [Analytics on Fast Data: Main-Memory Database Systems versus Modern Streaming Systems][17]

### Projects Presentations

* **April 27**: Flex spot: Massive Time Series Management Systems
    * [ModelarDB: Modular Model-Based Time Series Management with Spark and Cassandra][18]
    * [Waterwheel: Realtime Indexing and Temporal Range Query Processing over Massive Data Streams][19]
    * Project Presentations
* **May 04**:
    * Project Presentations

## Links

[1]: https://bit.ly/33UrRHy  
[2]: https://bit.ly/33SpdlR  
[3]: https://bit.ly/2QtsEM1 
[4]: https://bit.ly/32U9dOF 
[5]: https://bit.ly/372pxjM 
[6]: https://bit.ly/2NPRDXP 
[7]: ./papers/gorilla.pdf  
[8]: ./papers/btrdb.pdf  
[9]: ./papers/keogh_trillion.pdf 
[10]: ./papers/iSAX.pdf  
[11]: ./papers/sfa.pdf  
[12]: ./papers/coconut.pdf  
[13]: ./papers/weasel_muse.pdf  
[14]: ./papers/Kafka.pdf  
[15]: ./papers/samza.pdf  
[16]: ./papers/efficient_streams_on_modern_hardware.pdf 
[17]: ./papers/mmdb_vs_streams.pdf  
[18]: ./papers/modelar.pdf  
[19]: ./papers/waterwheel.pdf  
[20]: https://www.youtube.com/watch?v=xwnwVeYlP8o
