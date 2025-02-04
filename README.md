# HackRF-and-RTL-SDR-to-scan-satellite-signals

step-by-step guide to get started with scanning satellite communications.

📡 1. Hardware Requirements
RTL-SDR (budget option, limited frequency range)
HackRF One (full-duplex SDR with a wider frequency range)
NooElec SAWbird LNA (for boosting weak signals)
Wideband Antenna (e.g., helical, yagi, or dish antennas)
Low-Noise Amplifier (LNA) (to enhance weak signals)
Band-Pass Filter (to remove unwanted noise)

⚙️ 2. Software Setup
You’ll need SDR software to process and analyze signals. Here are common tools:

SDR# (SDRSharp) – Best for RTL-SDR, beginner-friendly
GQRX – Cross-platform alternative
GNURadio – Advanced signal processing
SatDump – Satellite image decoding
WXtoImg – NOAA weather satellite image decoding
Orbitron – Real-time satellite tracking

🚀 3. Track Satellite Frequencies
You need satellite frequency data to know what signals to scan. Use:

SatNOGS DB (https://db.satnogs.org/)
Gunter’s Space Page (https://space.skyrocket.de/)
N2YO (https://www.n2yo.com/) for live tracking
🔹 Common Satellite Frequencies:

    “| Satellite Type | Frequency Range | | --- | --- | | NOAA Weather | 137–138 MHz | | GOES Weather | 1.69 GHz | | Inmarsat L-Band | 1.54 GHz | | Iridium | 1.616 GHz | | GPS | 1.575 GHz | | Amateur Radio Sats | 145-146 MHz & 435-438 MHz | | ISS SSTV | 145.800 MHz |”

📻 4. Receiving Signals
Using RTL-SDR:
Connect your RTL-SDR and antenna.
Open SDR# or GQRX.
Set Frequency (e.g., 137 MHz for NOAA).
Choose NFM (Narrowband FM) mode for voice/data or USB/LSB for weak signals.
Adjust gain and filter settings to improve reception.
Using HackRF:
Open GNURadio or SDR#.
Tune to higher frequency satellites (L-band, S-band).
Use external LNA and filters for weak signals.
Record and demodulate signals with GNURadio.

🌍 5. Decoding Satellite Signals
Some satellites transmit raw telemetry, APRS, SSTV, or weather images.

Weather Sats (NOAA/GOES): Use WXtoImg to decode images.
APRS (Amateur Packet Reporting System): Use Direwolf or Multimon-NG.
SSTV (Slow Scan TV from ISS): Use RX-SSTV to decode images.
Inmarsat L-band (Marine, Aviation Data): Use JAERO.

🛰️ 6. Real-Time Satellite Tracking
Use Orbitron or Gpredict to predict satellite passes over your location.

Enter your GPS coordinates.
Select target satellite.
Note the Doppler shift and adjust frequency accordingly.
⚠️ Legal Disclaimer
DO NOT TRANSMIT on satellite bands (FCC/ITU regulations).
DO NOT DECRYPT encrypted military or commercial signals.
DO NOT INTERFERE with licensed satellite operations.
