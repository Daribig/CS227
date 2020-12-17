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

## Resrouces and Meeting

If you want extra resources or to schedule a meeting, set an appointment at
[https://bit.ly/38genHt][36]

## Projects

You'll also be working on projects that involve modern or even novel techniques
to address a research question. We have our own ideas that we prefer you work on
or at least guide your project. We are also open to your own ideas if none of
these ideas appeal to you.

We're actually pretty adamant that you work on our ideas.

### Project Goal by student demographic

### Project Requirements

* Significant coding portion that implements your research
* Will likely be written in Rust - We'll provide as much support as needed to
  get you up to speed
* A write up that describes what you did and how you did it, along with
  benchmarks or other measurements that you use to show whether your hypothesis
  was verified or not. (Not all "good" hypotheses are verified!)
* At end of class, we'll all have presentations. The logistics for this is still
  tbd

### Project Process

### Project options

### Project Assignments

## Readings

The schedule below follows the readings we for every week. Although these
readings are the specifics we want to cover during the class, feel free to read
more material directly related to but not included in the readings.

**Reading Summaries** for the day's are to be submitted before class. These
summaries are pretty free-form but generally speaking we want you to compare and
contrast the approaches in each of the papers.

Submit your reading summaries here: TBD

([top](#table-of-contents))

## Schedule

### Reading assignments

Can be found here: TBD

### Topic: Introduction to Time Series Management Systems

* **January 25**:
    * Introductions to the class logistics
    * An overview of timeseries databases and workloads
    * Some helpful material to whet your appetite:
        * [Goku: Pinterest’s in-house time-series database (Video)][23]
        * [Spark ITS: Indexing for Large Scale Time Series Data on Apache Spark][24]

### Topic: Time Series Data and Storage

* **February 1**: Prometheus
    * [Implementing Prometheus][1]
    * Prometheus details:
        * [Part 1][2]
        * [Part 2][3]
        * [Part 3][4]
        * [Part 4][5]
* **February 8**: Prometheus Issues
    * [Challenges using Prometheus at scale][6]
    * [Containing your cardinality][7]
* **February 15**: No classes

* **February 22**: Other storage strategies
    * [TimeScaleDB][8]
    * [BTrDB: Optimizing Storage System Design for Time Series Processing][9]
* **March 1**: TSDBs at scale
    * [Google Monarch][10]
    * [M3 Architecture - From "Overview" to "Caching"][11]

### Topic: Time Series Analysis

* **March 8**: Analytics Databases
    * [Plato: Approximate Analytics over Compressed Time Series with Tight Deterministic Error Guarantees][12]
    * [Timon: A Timestamped Event Database for Efficient Telemetry Data Processing and Analytics][13]

* **March 15**: Anomaly Detection
    * [Series2Graph: Graph-based Subsequence Anomaly Detection for Time Series][14]
    * [Time-Series Anomaly Detection Service at Microsoft][15]
    * TODO: Are there other better ones out there?

* **March 22**: Representation Learning
    * [GRAIL: Efficient Time-Series Representation Learning][16]
    * [Continuously Adaptive Similarity Search][17]

### Topic: Observability
* **March 29**: Metrics
    * [Seer: Leveraging Big Data to Navigate the Complexity of Performance Debugging in Cloud Microservices][18]
    * [Sieve: Sieve: Actionable Insights from Monitored Metrics in Microservices][19]
* **April 5**: Traces
    * [Pivot Tracing: Dynamic Causal Monitoring for Distributed Systems][20]
    * [Canopy: An End-to-End Performance Tracing And Analysis System][21]
* **April 12**: Observability
    * [The Kaiju Project: Enabling Event-Driven Observability][22]

## Topic: Project Presentations
* **April 19**: TBD

([top](#table-of-contents))

## Links

[1]: https://bit.ly/37uwAUV  
[2]: https://ganeshvernekar.com/blog/prometheus-tsdb-the-head-block/  
[3]: https://ganeshvernekar.com/blog/prometheus-tsdb-wal-and-checkpoint/  
[4]: https://ganeshvernekar.com/blog/prometheus-tsdb-mmapping-head-chunks-from-disk/  
[5]: https://ganeshvernekar.com/blog/prometheus-tsdb-persistent-block-and-its-index/  

[6]: https://sysdig.com/blog/challenges-scale-prometheus/  
[7]: https://www.youtube.com/watch?v=49BGvC1coG4  

[8]: https://blog.timescale.com/blog/time-series-data-why-and-how-to-use-a-relational-database-instead-of-nosql-d0cd6975e87c/  
[9]: ./papers/btrdb.pdf  

[10]: http://www.vldb.org/pvldb/vol13/p3181-adams.pdf  
[11]: https://m3db.github.io/m3/m3db/architecture/  

[12]: http://www.vldb.org/pvldb/vol13/p1105-lin.pdf  
[13]: http://www.cs.utah.edu/~lifeifei/papers/timon.pdf  

[14]: http://www.vldb.org/pvldb/vol13/p1821-boniol.pdf  
[15]: https://arxiv.org/pdf/1906.03821.pdf  

[16]: https://dl.acm.org/doi/pdf/10.14778/3342263.3342648  
[17]: https://dl.acm.org/doi/pdf/10.1145/3318464.3380601  

[18]: https://www.csl.cornell.edu/~delimitrou/papers/2019.asplos.seer.pdf  
[19]: https://arxiv.org/pdf/1709.06686.pdf  

[20]: https://cacm.acm.org/magazines/2020/3/243034-pivot-tracing/fulltext  
[21]: https://research.fb.com/wp-content/uploads/2017/10/sosp17-final14.pdf  

[22]: https://dl.acm.org/doi/pdf/10.1145/3401025.3401740  


[23]: https://atscaleconference.com/videos/scale-2018-goku-pinterests-in-house-time-series-database/  
[24]: https://www.youtube.com/watch?v=xwnwVeYlP8o  


[25]: https://arxiv.org/pdf/1702.03584.pdf  
[26]: https://arxiv.org/pdf/2010.02803.pdf  

