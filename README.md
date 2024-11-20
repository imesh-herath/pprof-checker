# PPROF Checker Script

This Bash script is a utility for profiling Go applications using the `pprof` tool. It allows users to collect and analyze memory and CPU usage data from a specified Go application running on a specified IP address. This script supports both Windows and Linux operating systems. 

## Features

- Collect heap, CPU profiling and health data from a running Go application.
- Display the top memory, goroutine and CPU usage.
- Display the health of the service.
- Option to open a web interface for detailed profiling visualization.
- Graceful cleanup of temporary files on script interruption.

## Prerequisites

- **Go**: Ensure that the Go programming language is installed on your system. You can check by running `go version` in your terminal.
- **pprof Endpoint**: Ensure that your Go application has the `pprof` endpoint enabled, typically accessible at `http://<IP_ADDRESS>:6060/debug/pprof/`.

## Installation

- You can copy the program to /usr/local/bin/ by below command.

  `sudo cp <downloaded_path>/profiler /usr/local/bin`

## Usage

To run the script, execute the following command, replacing `<profile_type>` with either `c` for CPU profiling or `h` for heap profiling, and `<IP_ADDRESS>` with the IP address of the target application:

./profiler <profile_type> <IP_ADDRESS>

### Arguments

- `<profile_type>`:
  - `c`: Collect CPU profiling data for 30 seconds.
  - `h`: Collect heap profiling data.
  - `g`: Collect goroutine profiling data.
  - `health`: Collect health data.
- `<IP_ADDRESS>`: The IP address of the target application from which to collect profiling data.

You can view detailed usage information by running:

`./profiler help`

This will display the available profiling types and the expected format for the IP address.

### Example Commands

- Collect Heap Profiling Data:

  `./profiler h 0.0.0.0`

- Collect CPU Profiling Data:

  `./profiler c 0.0.0.0`

- Collect Goroutine Profiling Data:

  `./profiler g 0.0.0.0`

- Collect Health status Data:

  `./profiler health 0.0.0.0`

- View Help Information:

  `./profiler help`

## Script Behavior

When the script is executed, it will:

- Check for the required arguments and display help information if necessary.
- Collect profiling data based on the specified type.
- Show the top memory, goroutine or CPU usage in the terminal.
- Show the health status in the terminal.
- Prompt the user to open a web interface for detailed profiling analysis.
- Clean up any temporary files used during execution.

## Author

**Imesh Herath**  
Email: imeshnipun2000@gmail.com
