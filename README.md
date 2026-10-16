# Network Performance Monitoring System

## 1. Project Overview

The Network Performance Monitoring System is a Python-based application developed as a Computer Communication Networks (CCN) microproject. It measures and displays important network performance parameters through an interactive dashboard.

The system measures network latency, jitter, packet loss, and download throughput. It also stores test results in a CSV file and displays graphs to help users understand network performance over time.

## 2. Objectives

- To measure network latency using ping requests.
- To calculate jitter from successful latency measurements.
- To calculate the percentage of packet loss.
- To measure download throughput.
- To display network measurements using an interactive dashboard.
- To save test results for future reference.
- To analyze and compare network performance across multiple tests.
- To test how the system handles invalid hostnames and network errors.

## 3. Features

- **Latency Measurement:** Measures the time taken for ping responses.
- **Jitter Calculation:** Calculates the average absolute difference between consecutive successful latency measurements.
- **Packet Loss Calculation:** Calculates the percentage of packets that did not receive a response.
- **Throughput Measurement:** Estimates download speed in Mbps by downloading test data.
- **Interactive Dashboard:** Displays measurements and graphs using Streamlit.
- **Test History:** Stores measurement records in a CSV file.
- **Performance Analysis:** Provides a basic interpretation of the recorded results.
- **Error Handling:** Displays an error message when ping requests do not receive replies.

## 4. Technologies Used

- Python
- Streamlit
- Pandas
- Plotly
- CSV for storing test history
- Visual Studio Code (VS Code)

## 5. Project Structure

```text
CCN_Network_Monitoring/
│
├── app.py
├── network_monitor.py
├── test_monitor.py
├── verify_calculations.py
├── requirements.txt
├── README.md
│
├── data/
│   └── network_history.csv
│
└── .venv/
```

**Note:** The `.venv` folder contains the Python virtual environment. It should not normally be uploaded to GitHub.

The `network_history.csv` file is created when test results are saved.

## 6. Installation and Setup

### Step 1: Install Python

Install Python on your computer if it is not already installed.

### Step 2: Open the project

Open the project folder in Visual Studio Code.

### Step 3: Create a virtual environment

Open the VS Code terminal and run:

```powershell
py -3.14 -m venv .venv
```

### Step 4: Activate the virtual environment

```powershell
.\.venv\Scripts\Activate.ps1
```

### Step 5: Install the required libraries

```powershell
python -m pip install -r requirements.txt
```

## 7. Running the Application

Run the following command in the VS Code terminal:

```powershell
python -m streamlit run app.py
```

The dashboard will open in your browser. If it does not open automatically, visit:

http://localhost:8501

Keep the terminal running while using the dashboard.

## 8. How to Use the System

1. Open the dashboard in your browser.
2. Enter the hostname or IP address to test.
3. Select the number of ping packets.
4. Click **Start Measurement** to measure latency, jitter, and packet loss.
5. Click **Measure Throughput** to measure download speed.
6. View the results and graphs.
7. Check the network test history.
8. Review the performance analysis section to understand the results.

An active internet connection is generally required for the network tests. Ping results may also depend on firewall rules and network configuration.

## 9. Performance Parameters

| Parameter | Description | Unit |
|---|---|---|
| Latency | Time taken to receive a ping response | Milliseconds (ms) |
| Jitter | Variation between consecutive successful latency measurements | Milliseconds (ms) |
| Packet Loss | Percentage of sent packets that did not receive a response | Percentage (%) |
| Throughput | Measured download data rate | Megabits per second (Mbps) |

## 10. Testing and Results

The project was tested using calculation verification and actual network measurements.

Five calculation verification tests passed:

1. Jitter calculation using multiple latency values.
2. Packet loss when some packets are lost.
3. Packet loss when all packets are received.
4. Packet loss when no packets are received.
5. Jitter calculation with only one latency value.

Three recorded network tests to `1.1.1.1` produced these results:

| Test | Average Latency | Jitter | Packet Loss | Throughput |
|---|---:|---:|---:|---:|
| 1 | 118 ms | 59.50 ms | 0% | 6.70 Mbps |
| 2 | 98.2 ms | 58.75 ms | 0% | 2.25 Mbps |
| 3 | 90.8 ms | 12 ms | 0% | 4.67 Mbps |

These measurements are examples from the testing environment. Actual results may differ depending on the internet connection, network conditions, and time of testing.

During reliability testing, an invalid hostname produced a clear ping error message. The throughput test could still succeed independently, demonstrating that the two measurements use different network operations.

## 11. Limitations

- Network measurements can change with internet conditions.
- Some networks block ping requests.
- Throughput is estimated using a download test and may not represent the maximum speed of the internet connection.
- Jitter accuracy depends on the number and quality of successful latency measurements.
- A saved record may contain missing latency-related values if ping fails but throughput succeeds.
- The performance analysis uses simple thresholds and should be treated as indicative rather than universal.

## 12. Future Improvements

- Add automatic periodic measurements.
- Improve the identification of incomplete test records.
- Add configurable test hosts and download sizes.
- Add more detailed error logging.
- Export reports in PDF or Excel format.
- Add alerts when network performance falls below selected limits.

## 13. Conclusion

The Network Performance Monitoring System provides an interactive way to measure and analyze important network performance parameters. It measures latency, jitter, packet loss, and download throughput, while saving results for comparison. Calculation verification and reliability testing demonstrated that the main functions work in the tested conditions. The project helps users understand network performance and observe how measurements change over time.

## 14. Author

**Project:** Network Performance Monitoring System

**Subject:** Computer Communication Networks (CCN)

**Tools:** Python, Streamlit, Pandas, Plotly, and VS Code
