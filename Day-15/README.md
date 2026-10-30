# Day 15: Performance Testing Fundamentals

## 1. Learning Objectives
- Understand performance testing and its purpose.
- Identify important performance metrics.
- Install and explore Apache JMeter.
- Create basic load tests and analyze results.

## 2. What Is Performance Testing?
**Performance testing** evaluates a system's speed, stability, responsiveness, and resource usage under a particular workload.

**Why perform it?**
- Find slow response times and bottlenecks.
- Check stability under expected and heavy traffic.
- Understand system capacity.
- Reduce the risk of poor user experience or system failure.

**When to perform it:** When validating a new application or major release, before expected traffic peaks, after performance-related changes, and when investigating slow systems.

## 3. Types of Performance Testing
| Type | Meaning |
|---|---|
| Load testing | Checks behavior under expected and peak user load. |
| Stress testing | Pushes the system beyond normal capacity to find its limits. |
| Spike testing | Checks the effect of a sudden increase or decrease in traffic. |
| Endurance testing | Runs a sustained workload for an extended period. |
| Scalability testing | Checks how performance changes as workload or resources increase. |
| Volume testing | Checks behavior when handling large amounts of data. |

## 4. Performance Metrics
| Metric | Meaning |
|---|---|
| Response time | Time taken for a request to receive a response. |
| Throughput | Requests processed per unit of time, often requests/second. |
| Error rate | Percentage of requests that fail. |
| CPU usage | Processor capacity being used. |
| Memory usage | RAM consumed by the application or system. |
| Network bandwidth | Amount of data transferred over the network per unit of time. |

Interpret metrics together. A fast response time is not useful if many requests fail. CPU, memory, and network measurements generally require access to the system being tested.

## 5. Apache JMeter
**Apache JMeter** is an open-source tool used to test the performance of applications and services, including HTTP APIs and web applications.

**Installation**
1. Install a compatible Java version if it is not already installed.
2. Download the Apache JMeter binary distribution from the official Apache JMeter website.
3. Extract the downloaded archive.
4. Launch JMeter using the startup script in the `bin` directory (`jmeter.bat` on Windows).
5. Confirm that the JMeter GUI opens.

## 6. Main JMeter Components
| Component | Purpose |
|---|---|
| Test Plan | Top-level container for a test. |
| Thread Group | Defines virtual users (threads), ramp-up period, and loop count. |
| Sampler | Sends a request, such as an HTTP request. |
| Listener | Displays or stores test results. |
| Assertion | Checks whether a response meets an expected condition. |
| Timer | Adds a delay between requests. |

**Test plan diagram**
```text
Test Plan
   |
   +-- Thread Group
          |
          +-- HTTP Request (Sampler)
          +-- Timer (optional)
          +-- Assertion (optional)
          +-- Listeners
                 +-- View Results Tree
                 +-- Summary Report
```

## 7. Create Your First HTTP Load Test
1. Open JMeter and create a Test Plan.
2. Add a Thread Group.
3. Configure **Number of Threads** (virtual users), **Ramp-up Period** (time to start users), and **Loop Count** (executions per user).
4. Add an HTTP Request sampler.
5. Enter the authorized target server, path, and HTTP method.
6. Add View Results Tree and Summary Report listeners.
7. Run the test and inspect the results.

**Example configuration:** 5 users, a 10-second ramp-up, and 2 loops. This is an example only; select values appropriate to the system and permission you have.

## 8. JMeter Test Execution Flow
```text
Configure Thread Group
        |
Add HTTP Request Sampler
        |
Add Listeners and Assertions
        |
Run Test
        |
Review Response and Summary Metrics
        |
Record Findings
```

## 9. Practice Scenarios
| No. | Scenario | Focus |
|---:|---|---|
| 1 | Web application load test | Page/request response under multiple users. |
| 2 | API load test | API response time, throughput, and failures. |
| 3 | Database load test | Database performance under an approved workload. |
| 4 | Gradual load increase | Observe metrics as virtual users increase. |
| 5 | Breaking-point test | Identify where errors or response times become unacceptable. |

Only test systems you own or have explicit permission to test. Do not run load or stress tests against public practice services without authorization. For database testing, use an approved test environment and a suitable database driver or application endpoint.

## 10. Analyze Test Results
Review average and percentile response times (when available), throughput, error count and percentage, and CPU, memory, and network usage where monitoring access is available.

Record the test configuration, target, duration, result metrics, errors, and observations. Compare runs only when workload and environment are comparable.
