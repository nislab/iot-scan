# IoT-Scan Traces

Repository for accompanying materials to IoT-Scan.

## Data Format

Trace files contain anonymized activity time series of one or more device per file. Each trace file is a JSON-formatted text file containing the following data structure:

```json
{
    "src": <a hash of the source PCAP file path>,
    "entries": <number of entries>,
    "duration": <duration in seconds>,
    "devices": [
        <list of device hashes>
    ],
    "device_stats": {
        "samples": {
            <map of device IDs to their number of samples>
            ...
        },
        "mean": {
            <map of device IDs to their mean arrival times in seconds>
            ...
        },
        "lambda": {
            <map of device IDs to their arrival rates (assuming memorylessness)>
            ...
        },
        "stdev": {
            <map of device IDs to their standard deviation of arrival times>
            ...
        }
    },
    "time_series": [
        <list of [timestamp, device ID] tuples of device activity>
        ...
    ]
}

```