# Experiment Goals

We plan to use a HackRF One software defined radio to collect drone RF data in a low noise environment. The aim of our project is to prototype a drone detection system for the Georgia Tech Police Department. The system will use a software defined radio for RF spectrum analysis and apply machine learning methods to detect drone RF activiity. Capturing a drone's RF communication in a low noise environment will allow us to narrow down the most effective detection methods to implement for the GTPD.


# Experiment Parameters

Time required: 1-2 hours


We are primarily interested in the 2.4 Ghz frequency range. If time allows, we would also like to collect data in the 900 Mhz and 5.8 Ghz ranges.

# Experiment Plan

Use a HackRF, a laptop with GNU radio, and a provided DJI drone to collect RF spectrum data using HackRF Sweep for processing outside of the lab. The drone would be powered but not moving. Data will be collected from various distances and time intervals by moving the HackRF and the drone controller away and around the lab, if the size of the lab permits.

Before each recording we want to:
- Record environment noise for about 1 minute before starting our actual recording, to ensure we have an accurate control reading of the noise in the environment
(hackrf_sweep -f (lower_range):(upper range) -n 8192 -w 600000 -r control_{n}.csv)
- copy output file to another machine (Tegra has limited storage)
- Perform the actual recording

Recordings we want to obtain:
1. One minute of RF activity in which we know the drone is running (Full spectrum we think it could be operating in) 
(hackrf_sweep -f (lower_bound):(upper_bound) -n 8192 -w 600000 -r active_drone.csv)
2. A recording of RF activity as someone walks WITH the drone on from right next to the hackrf to about 100m away (Where ever we see activity from 1)
3. A recording of RF activity as someone walks with the drone from about 100m away to the hackRF (same spectrum as 2)
