# Assignment-5
Summer Analytic 2025-consultancy and analytic club,IITG

# Dynamic Pricing for Urban Parking Lots 🚗📈

**Capstone Project - Summer Analytics 2025**  
Hosted by: Consulting & Analytics Club × Pathway

## 📝 Project Objective

Urban parking spaces often suffer from either overutilization or underutilization due to static pricing. This project aims to build a **real-time, intelligent, dynamic pricing model** for 14 urban parking lots using demand, traffic, and competitor conditions.

The pricing model adjusts based on:

- Occupancy & queue length
- Nearby traffic congestion
- Special events/holidays
- Type of incoming vehicle
- Competitor parking prices

The base price for all lots starts at **$10**, and changes must be smooth, explainable, and bounded.

---

## 📂 Dataset Description

The dataset contains 73 days of data, sampled **every 30 minutes (18 time points per day)**, across **14 urban parking spaces**.

Each record includes:

- **Location info**: Latitude, Longitude  
- **Lot features**: Capacity, Occupancy, Queue Length  
- **Vehicle**: Type of incoming vehicle (car, bike, truck)  
- **Environment**: Traffic congestion level, Special day indicator  

---

## 🧠 Model Architecture

### ✅ Model 1: Baseline Linear Model
A simple model based on occupancy:
```
Price_{t+1} = Price_t + α * (Occupancy / Capacity)
```

### ✅ Model 2: Demand-Based Pricing
A multi-featured model using a demand function:
```
Demand = α*(Occupancy/Capacity) + β*QueueLength − γ*Traffic + δ*IsSpecialDay + ε*VehicleTypeWeight  
Price_t = BasePrice * (1 + λ * NormalizedDemand)
```
- Normalized and bounded demand
- Price range capped at [0.5×, 2×] base

### ✅ Model 3 (Optional): Competitive Pricing
Incorporates **proximity to other lots**:
- Uses lat-long distances to assess nearby competitor prices
- Adjusts price or suggests rerouting accordingly

---

## ⚙️ Tech Stack

- **Python** (only `numpy`, `pandas`, `pathway`)
- **Google Colab**
- **Bokeh** (for real-time visualizations)
- **Pathway** (for real-time data simulation and ingestion)

---

## 📊 Visualizations

Real-time visualizations using Bokeh:
- Line charts of dynamic price updates
- Comparison with competitor prices

---

## 🚀 How to Run

1. **Open the Colab notebook**  
2. **Run all cells in order** – this includes:
   - Data streaming via Pathway
   - Feature engineering
   - Real-time pricing logic
   - Visualization hooks

3. **Pricing outputs** and **visual plots** will update in real-time.

---

## 📘 Assumptions

- All vehicles value time equally
- Competitor prices are known and up-to-date
- Queue lengths directly influence demand
- Traffic impact is negatively correlated with willingness to pay

---

## 📎 References

- Pathway Docs:  
  https://pathway.com/developers/user-guide/introduction/first_realtime_app_with_pathway/

- Summer Analytics 2025:  
  https://www.caciitg.com/sa/course25/

---

## 👤 Contributors

- Palak Upadhyaya  

