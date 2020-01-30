# Everything is a Time Series

> What goes forward never back?  
> What's only coming, or has just past?  
> What goes loopy when you take crack?  
> What dilates when you go fast?  
>   -- <cite>some time series guy</cite>

> `$ git push origin hamster`  
>   -- <cite>same guy</cite>

## Table of Contents

* [What this class is about](#what-this-class-is-about)
* [Projects](#projects)
    * [Project Requirements](#project-requirements)
    * [Project Process](#project-process)
    * [Project Ideas](#project-ideas)
* [Schedule](#schedule)
    * [Introduction to Time Series Management Systems](#topic-introduction-to-time-series-management-systems)
    * [Time Series Data and Storage](#topic-time-series-data-and-storage)
    * [Time Series Similarity Search](#topic-time-series-similarity-search)
    * [Massive Time Series](#topic-massive-time-series)
    * [Projects Presentations](#topic-projects-presentations)


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

([top](#table-of-contents))

## Projects

You'll also be working on projects that involve modern or even novel techniques
to address a research question. We have our own ideas that we prefer you work on
or at least guide your project. We are also open to your own ideas if none of
these ideas appeal to you.

We're actually pretty adamant that you work on our ideas.

### Project Goal by student demographic

We want you to leave with a significant amount of code.

* For non-PhDs, this is a great software artifact to present to potential
  employers.
* For Sophomores/Juniors, this is our opportunity to convince you that you
  should do research with us!
* For PhDs, well it's a cool project and our questions are things we really do
  plan on writing papers on (and yours could become one!)

### Project Requirements

* Significant coding portion that implements your research
* Will likely be written in Rust - We'll provide as much support as needed to
  get you up to speed
* A write up that describes what you did and how you did it, along with
  benchmarks or other measurements that you use to show whether your hypothesis
  was verified or not. (Not all "good" hypotheses are verified!)
* We'll have regular checkins in class:
    * Week of February 10: project selection or proposal
    * Weeks of February 24 - March 9: Round-robin progress check-ins
    * Subsequent weeks: Project update presentations for 2 groups e/a week until
      everyone has presented
* At end of class, we'll all have presentations. The logistics for this is still
  tbd

### Project Process

We stand on the shoulder of giants so we don't just go into it blindly. We'll
first implement something based on the current state of the art (SotA), and then
find its shortcomings. After implementing it or learning more about the
workloads that we expect we handle, we'll have some hypothesis of what workloads
the SotA excels and where it might not.

We then test our hypothesis by building a few experiments that show this to be
the case. Finally, we implement our ideas for how it could work better. It could
be a completely new structure, or an improvement on the current SotA
implementation. Then we use the experiments we designed to show that our
solution works or doesn't.

### Project options

**Dynamic Time Warping in Multiple Dimensions**
* Is there a way to design a lower-bounding measure for Dynamic Time Warping in
multiple dimensions? [Papers][30]

**Compressed Time Series Storage**
* Gorilla, Sprintz, and similar compression/storage techniques ignore the
existence of tags in the ingested TS. Can we design a TS storage engine that
takes tags as a first-class citizen? [Papers][31]

**Multidimensional Time Series Similarity Search Index**
* Can we design a time series index without the need to use machine learning or
initial data that supports multidimensional time series similarity search?
[Papers][32]

**Time Series Data Representation**
* Current symbolic time series representations fail to be data adaptive. Can we
find a way to make symbolic representations data-adaptive. [Papers][33]

([top](#table-of-contents))

## Schedule

### Topic: Introduction to Time Series Management Systems

* **January 27**:
    * Introductions to the class logistics
    * An overview of timeseries databases and workloads
    * Some helpful material to whet your appetite:
        * [InfluxDB's sell on TSDBs][2]
        * [Goku: Pinterest’s in-house time-series database (Video)][1]
        * [Spark ITS: Indexing for Large Scale Time Series Data on Apache Spark][20]

### Topic: Time Series Data and Storage

* **Febuary 03**: Storage in the wild
    * [Prometheus Storage Overview][3] and [Details][4]
    * [InfluxDB Storage][5]
* **February 10**: Storage in papers (Compression)
    * [Gorilla: A Fast, Scalable, In-Memory Time Series Database][7]
    * [Sprintz][27]
* **Febuary 17**:
    * No class - Project literature review!
* **February 24**: More Storage in papers (Alternative Strategies)
    * [BTrDB: Optimizing Storage System Design for Time Series Processing][8]
    * [The TileDB Array Data Storage Manager][24]; This is a funded
    [company][25] with well [documented apis and file formats][26]
* **March 02**: Industry Papers on Time Series(ish) Databases
    * [Druid][28]; This is one among many "massively distributed OLAP systems"
    and is frequently considered a TSDB
    * [Bigtable: A Distributed Storage System for Structured Data][29]; This is
    a foundational paper for the wide column store data model used in HBase and
    Cassandra which are in turn, the foundations of OpenTSDB, KairosDB, and
    others.

### Topic: Time Series Similarity Search

* **March 09**: Distance Measures
    * [Searching and Mining Trillions of Time Series Subsequences under Dynamic Time Warping][9]
    * [The Lernaean Hydra of Data Series Similarity Search: An Experimental Evaluation of the State of the Art][23]
* **March 16**: Indexing
    * [Coconut: A Scalable Bottom-Up Approach for Building Data Series Indexes][12]
    * [Scalable, Variable-Length Similarity Search in Data Series: The ULISSE Approach][21]
* **March 23**: Spring Break (Background/easy reading)
    * [iSAX: Indexing and Mining Terabyte Sized Time Series][10]
    * [SFA: A Symbolic Fourier Approximation and Index for Similarity Search in High Dimensional Datasets][11]
* **March 30**: Clustering
    * [Multivariate Time Series Classification with WEASEL+MUSE][13]
    * [k-Shape: Efficient and Accurate Clustering of Time Series][22]

### Topic: Massive Time Series
* **April 06**: Foundations of Stream Processing at Scale
    * [Kafka: a Distributed Messaging System for Log Processing][14]
    * [Samza: Stateful Scalable Stream Processing at LinkedIn][15]
* **April 13**: Modern Hardware
    * [Analyzing Efficient Stream Processing on Modern Hardware][16]
    * [Analytics on Fast Data: Main-Memory Database Systems versus Modern Streaming Systems][17]

### Projects Presentations

* **April 20**
    * [ModelarDB: Modular Model-Based Time Series Management with Spark and Cassandra][18]
    * [Waterwheel: Realtime Indexing and Temporal Range Query Processing over Massive Data Streams][19]
* **April 27** What's happening here? The stars shall align and time shall
  dilate
    * Observability?
    * Project Presentations
* **May 04**:
    * Project Presentations

([top](#table-of-contents))

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
[21]: ./papers/ulisse.pdf  
[22]: ./papers/kshape.pdf
[23]: ./papers/learnaean.pdf
[24]: ./papers/tiledb.pdf
[25]: https://tiledb.com
[26]: https://docs.tiledb.com/main/
[27]: ./papers/sprintz.pdf
[28]: ./papers/druid.pdf
[29]: ./papers/bigtable.pdf
[30]: dtw_papers.md
