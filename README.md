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

    “| Satellite Type     | Frequency Range |
     | NOAA Weather       | 137–138 MHz | 
     | GOES Weather       | 1.69 GHz | 
     | Inmarsat L-Band    | 1.54 GHz | 
     | Iridium            | 1.616 GHz | 
     | GPS                | 1.575 GHz | 
     | Amateur Radio Sats | 145-146 MHz & 435-438 MHz | 
     | ISS SSTV           | 145.800 MHz |”

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


🛠️ Step 1: Choosing a Target Satellite

First, decide what type of satellite signals you want to receive:

    Weather Satellites (NOAA, GOES) → Receives weather images
    Amateur Radio Sats (ISS, SO-50, AO-91) → APRS, SSTV, Voice
    Navigation Satellites (GPS, Galileo, GLONASS) → Positioning signals
    Communications Satellites (Inmarsat, Iridium) → L-band data, voice
    Use N2YO or Gpredict to track satellites and find their frequencies.

📌 Recommended Tracking Tools:

    🔗 SatNOGS Database → Find active satellite frequencies
    🔗 N2YO → Live satellite tracking
    🔗 Gpredict → Predict satellite passes
    
📡 Step 2: Setting Up Your Hardware

For RTL-SDR (Beginner)
    
    ✅ Works well for 137-138 MHz (NOAA Weather, Amateur Radio)
    ✅ Affordable but limited to ~1.7 GHz max

Required Equipment:

    RTL-SDR v3
    V-Dipole or Helical Antenna (for NOAA weather sats)
    Low-Noise Amplifier (LNA) (to boost weak signals)
    Band-Pass Filter (to remove interference)
    
For HackRF (Advanced)

    ✅ Covers a wider 1 MHz – 6 GHz range (L-band, S-band)
    ✅ Can capture higher frequency signals (Inmarsat, Iridium, GPS)

Required Equipment:

    HackRF One
    Helical, Yagi, or Parabolic Dish Antenna (depends on frequency)
    Bias-T LNA (e.g., NooElec SAWbird) for weak signals
    TCXO Module (reduces frequency drift)
    
⚙️ Step 3: Installing SDR Software

    Choose software depending on your SDR and OS:

📌 Windows:

    SDR# (SDRSharp) → Best for RTL-SDR
    WXtoImg → NOAA Weather decoding
    Orbitron → Real-time satellite tracking
    
📌 Linux (ParrotOS, BlackArch):

    sudo apt install gqrx-sdr gnuradio gr-satellites sox
    SatDump → Powerful satellite signal decoder
    sudo apt install rtl-sdr hackrf (for SDR drivers)
    
🛰️ Step 4: Receiving Satellite Signals

    🔹 NOAA Weather Satellites (137 MHz)
    1️⃣ Open GQRX or SDR#
    2️⃣ Set frequency to 137.1 - 137.9 MHz
    3️⃣ Choose Narrowband FM (NFM) mode
    4️⃣ Adjust gain & filter to reduce noise
    5️⃣ Save the audio file & decode with WXtoImg

🎯 Example Frequencies:

    NOAA-18: 137.9125 MHz
    NOAA-19: 137.1000 MHz
    Meteor-M2 (Digital): 137.900 MHz
    
🔹 ISS (International Space Station) SSTV & APRS

    SSTV Images: 145.800 MHz (Slow-Scan TV)
    APRS Packets: 145.825 MHz (Automatic Packet Reporting System)
    Use RX-SSTV to decode ISS images.

🔹 L-Band Communications (1.5 – 1.7 GHz)

    Requires HackRF + LNA + SAW filter.

📡 Common Signals:

    Inmarsat (1.54 GHz) → Maritime, aviation text messages
    Iridium (1.61 GHz) → Satellite phones
    GOES Weather (1.69 GHz) → High-resolution weather data
    
📌 Software for Decoding:

    JAERO (Inmarsat ACARS decoding)
    SatDump (GOES satellite image decoding)

⚠️ Legal Considerations

    ✅ Legal: Passive signal reception & analysis
    🚫 Illegal: Transmitting, decrypting private/military signals
