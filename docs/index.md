# Continuous Intelligence

This site provides documentation for this project.
Use the navigation to explore module-specific materials.

## How-To Guide

Many instructions are common to all our projects.

See
[⭐ **Workflow: Apply Example**](https://denisecase.github.io/pro-analytics-02/workflow-b-apply-example-project/)
to get these projects running on your machine.

## Project Documentation Pages (docs/)

- **Home** - this documentation landing page
- **Project Instructions** - instructions specific to this module
- **Your Files** - how to copy the example and create your version
- **Glossary** - project terms and concepts

## Additional Resources

- [Suggested Datasets](https://denisecase.github.io/pro-analytics-02/reference/datasets/cintel/)


## Custom Project

### Dataset
15 observations of system metrics recorded every 5 minutes from 08:00 to 09:10.
Each row contains a timestamp, request count, error count, and total latency in milliseconds.

### Signals
Used: requests, errors, total_latency_ms.
Created: error_rate (errors / requests), plus 3-observation rolling means for all four signals.

### Experiments
Applied a rolling window of size 3 to smooth short-term fluctuations.
Added a normalized error rate to make failure levels comparable across different traffic volumes.

### Results
All signals trend upward over the session. Error rate rises from 1.7% to 4.3%.
A dip occurs around 08:35–08:45 as number of requests decreases, then resumes climbing.
Rolling means confirm the rise is sustained, not just isolated spikes.

### Interpretation
The system handles light traffic well but degrades under load.
Errors grow faster than requests. Latency follows the same pattern,
reinforcing that performance drops as demand increases.
Early warning signs appear around 08:20, before traffic peaks.
