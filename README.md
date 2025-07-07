

🏙️ Dynamic Urban Parking Pricing with Real-Time Data Streaming
================================================================

📌 Description:
This project simulates an intelligent, real-time pricing engine for urban parking spaces.
It uses live-like streaming data, economic pricing models, and basic ML logic to dynamically
adjust prices based on demand, congestion, and real-world conditions.

✅ Features:
- Ingests real-time parking lot data using Pathway’s stream engine
- Combines static lot info with dynamic traffic, queue, and occupancy data
- Implements Model 1 (baseline linear pricing)
- Framework ready for Model 2 (demand-based) and Model 3 (rerouting + competition)
- Built with: Python, Pandas, NumPy, and Pathway

🧠 Problem Motivation:
Urban parking spaces are limited and often inefficiently priced.
Fixed prices lead to overcrowding in busy lots and underutilization in others.
Dynamic pricing improves efficiency, utilization, and driver experience.

🎯 Objective:
Build a dynamic pricing system that:
- Starts at a base price of $10
- Adjusts prices based on real-time occupancy and capacity (Model 1)
- Supports extension to smarter models using queue length, traffic, special events, vehicle type
- Suggests rerouting when lots are full (Model 3)

📈 Models:
Model 1: Linear pricing
    price = base + α * (occupancy / capacity)

Model 2: Demand-based pricing (planned)
    price = base * (1 + λ * normalized_demand_score)

Model 3: Smart rerouting + competition-aware pricing (optional)

📂 Input Data:
- 14 parking lots × 73 days, sampled every 30 minutes
- Columns: Timestamp, Lot ID, Occupancy, Capacity, QueueLength, VehicleType, Traffic, Events

📦 Output:
- Real-time stream of dynamic prices per lot
- Console logs or dashboard-ready price stream
- Easily extendable for plots or file outputs

Author: Anju Yadav

