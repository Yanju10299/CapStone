"""
===================================================================
🚗 Dynamic Urban Parking Pricing System (Real-Time with Pathway)
===================================================================

📌 Description:
This project simulates a real-time, intelligent dynamic pricing engine for urban parking spaces 
using streamed data, basic ML logic, and economic principles. Prices are updated continuously 
based on lot occupancy, traffic, queue length, and events.

🧠 Motivation:
Static parking prices cause overcrowding or underuse. This project builds a responsive pricing 
system to optimize space utilization and driver satisfaction in busy urban areas.

🎯 Objective:
- Base price starts at $10
- Price increases with occupancy
- Supports advanced pricing based on queue, traffic, events, and vehicle type
- Optional: rerouting logic when lots are full

🧰 Tech Stack:
- Python 3.11+
- Pandas & NumPy (data processing)
- Pathway (real-time data streaming)
- Matplotlib or Bokeh (optional plots)
- Google Colab / Jupyter Notebook (for testing)

🗂️ Input Data:
- 14 parking lots × 73 days
- 18 samples per day (every 30 min)
- Fields: Timestamp, Lot ID, Occupancy, Capacity, QueueLength, Traffic, VehicleType, Events

⚙️ Project Workflow:
1. Load raw dataset (CSV)
2. Combine LastUpdatedDate + Time → Timestamp
3. Sort by time and save essential features
4. Simulate streaming with `Pathway.demo.replay_csv()`
5. Extract full datetime (`t`) and date (`day`)
6. Apply pricing logic (Model 1 → Model 2 → Model 3)
7. Output real-time price stream

📈 Pricing Models:

MODEL 1 — Linear Pricing:
    price = base + α * (occupancy / capacity)

MODEL 2 — Demand-Based Pricing:
    demand = α1*(occupancy/capacity) + β*queue - γ*traffic + δ*event + ε*vehicle
    price = base × (1 + λ × normalized_demand)

📦 Output:
- Real-time prices per lot printed to console
- Optional CSV export or visualization

🧭 Architecture Flow:

    Raw CSV --> Preprocessing --> Feature CSV --> Stream (Pathway)
                                  |
                                  v
                            Time Parsing
                                  |
                                  v
                         Pricing Model (1,2,3)
                                  |
                                  v
                         Output (console/plot)

📂 Project Structure:

urban-parking-pricing/
├── dataset (1).csv              # Raw parking data
├── parking_stream_full.csv      # Cleaned data for stream input
├── main.py                      # Main simulation pipeline
├── model1_pricing.py            # Pricing logic (modular)
├── README.md                    # GitHub ReadMe file
└── report.pdf                   


👤 Author:
- Anju Yadav


🔗 Requirements:
Install via pip:
    pip install pathway pandas numpy matplotlib bokeh
"""


