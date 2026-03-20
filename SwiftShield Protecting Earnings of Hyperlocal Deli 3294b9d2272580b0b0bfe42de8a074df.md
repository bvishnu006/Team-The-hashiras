# SwiftShield: Protecting Earnings of Hyperlocal Delivery Partners

# Persona: Cloud Kitchen Instant Delivery Partners

## Disruption Framework

### 1. **Unlucky Situations**

**Examples:**

- Customer not responding at doorstep
- Customer unavailable (e.g., train departed / unreachable)
- Last-minute order cancellation

**Impact (Loss of Income):**

- Failed delivery attempt → no payout or reduced payout
- Time wasted per order (10–20 mins) → fewer deliveries per hour
- Reduced daily earnings due to incomplete orders

---

### 2. **Unsafe Locations & Situations**

**Examples:**

- Theft / robbery during delivery
- Violent or unsafe neighborhoods
- Sudden extreme threats (e.g., conflict situations, security alerts)

**Impact (Loss of Income):**

- Forced delivery abandonment → zero earnings for that order
- Temporary zone avoidance → reduced serviceable area
- Early shift termination → loss of remaining earning hours

---

### 3. **Unmarked / Hard-to-Find Households**

**Examples:**

- Missing house numbers
- Incorrect addresses
- Poor navigation / confusing layouts

**Impact (Loss of Income):**

- Increased delivery time per order → fewer orders completed
- Higher chances of order cancellation
- Lower efficiency → reduced earnings per hour

---

### 4. **Environmental Disruptions**

**Examples:**

- Extreme heat
- Heavy rain / floods
- Severe pollution

**Impact (Loss of Income):**

- Unable to operate safely outdoors
- Delivery demand drops or platform restrictions
- Reduced working hours → direct income loss

---

### 5. **Social Disruptions**

**Examples:**

- Sudden curfews
- Local strikes
- Market / zone closures

**Impact (Loss of Income):**

- No access to pickup/drop locations
- Orders unavailable → zero earnings during disruption
- Forced downtime during peak hours

---

# 🚀 1. PARAMETRIC TRIGGERS (Exact Payout Conditions)

These are **objective, measurable conditions** → once triggered, payout happens **automatically (no manual claims)**.

---

## 🔹 A. Unlucky Situations (Platform + App Data Driven)

**Trigger Conditions:**

- ≥ **2 failed delivery attempts** in a shift due to:
    - Customer not responding (OTP not confirmed within X mins)
    - Customer unreachable (call logs show ≥3 attempts)
- ≥ **2 last-minute cancellations** (after pickup or within 2 mins of arrival)

**Payout Logic:**

- ₹20–₹40 per failed attempt
- OR % of expected delivery fee (e.g., 50%)

---

## 🔹 B. Unsafe Locations & Situations (Geo + Risk Feed Based)

**Trigger Conditions:**

- Delivery partner enters **high-risk geo-zone** (crime index threshold exceeded)
- OR **delivery aborted** due to safety alert (panic button / app log)
- OR **official alerts** (police/security API flags zone)

**Payout Logic:**

- Fixed payout per aborted delivery (₹50–₹100)
- Bonus if shift is ended early → compensation for **remaining hours**

---

## 🔹 C. Unmarked / Hard-to-Find Households (Efficiency Loss Based)

**Trigger Conditions:**

- Delivery time exceeds **1.5× expected ETA** due to location issues
- OR GPS mismatch detected (>100m deviation at drop point)
- OR ≥2 customer clarification calls logged

**Payout Logic:**

- ₹10–₹25 per delayed delivery
- OR efficiency compensation (e.g., “lost order opportunity” payout)

---

## 🔹 D. Environmental Disruptions (Weather API Based)

**Trigger Conditions (API-based):**

- Rainfall > X mm/hr
- Temperature > 42°C
- AQI > 300
- Flood alerts issued

**Payout Logic:**

- **Hourly compensation** (₹50–₹80/hr) if active
- OR **flat daily payout** if deliveries halted

---

## 🔹 E. Social Disruptions (Government / Platform Signals)

**Trigger Conditions:**

- Curfew announced (geo-tagged)
- Zone marked “inactive” by platform
- Strike events → order volume drops > 60%

**Payout Logic:**

- ₹100–₹300 per affected shift
- OR % of average daily earnings

---

# 🤖 2. AI RISK MODEL FEATURES

Our AI decides: **How risky a worker’s upcoming week is → dynamic premium**

---

## 🔹 Input Features for out model

### 1. Worker Behavior Features

- Avg deliveries/day
- Cancellation rate
- Failed delivery ratio
- Average delivery time

### 2. Location-Based Risk

- Area crime index
- Address density quality (slums vs planned areas)
- Historical failure rates in that zone

### 3. Environmental Risk

- Weather forecast (next 7 days)
- AQI predictions
- Flood-prone zones

### 4. Platform Signals

- Order demand volatility
- Zone closure frequency
- Peak-hour dependency

### 5. Temporal Patterns

- Weekend vs weekday earnings
- Time-of-day risk (night deliveries = higher risk)

### 6. Worker previous history

- Does he had done any tampering of things like GPS to false claim insurance
- Had any crimianl cases or links with local gangs

---

## 🔹 Model Output

- **Risk Score (0–1 or Low/Medium/High)**
- **Expected Income Loss (₹/week)**

---

## 🔹 Models that are planned to use

- **XGBoost**
- **LSTM** ( for demand prediction)

---

# 💰 3. WEEKLY PRICING LOGIC

## 🔹 Step 1: Estimate Expected Weekly Loss

```
Expected Loss = Σ (Probability of disruption × Avg loss per event)
```

Example:

- Rain probability: 30% → loss ₹300
- Failed deliveries: 20% → loss ₹200

👉 Total Expected Loss = ₹500

---

## 🔹 Step 2: Add Safety Margin

- Platform adds 20–30% margin

👉 Premium = ₹500 × 1.25 = ₹625/week

---

## 🔹 Step 3: Personalization

- Low-risk worker → ₹300/week
- High-risk worker → ₹700/week

---

## 🔹 Step 4: Tier-Based Plans

| Plan | Weekly Premium | Coverage |
| --- | --- | --- |
| Basic | ₹199 | Only weather + social |
| Standard | ₹399 | + unlucky + address issues |
| Premium | ₹699 | All disruptions + higher payouts |

**Note:** *Our pricing is based on **expected loss modeling**, not arbitrary pricing*

---

# ⚙️ 4. PARAMETRIC AUTOMATION PLAN (END-TO-END FLOW)

---

## 🔹 Step 1: Data Collection

- Weather APIs
- GPS tracking
- Delivery logs
- Call logs
- Platform APIs

---

## 🔹 Step 2: Real-Time Monitoring Engine

- Continuously checks:
    - Weather thresholds
    - Delivery failures
    - Zone alerts

---

## 🔹 Step 3: Trigger Engine

- If condition met → trigger event
    
    Example:
    

```
IF rain > threshold AND worker active → trigger payout
```

---

## 🔹 Step 4: Fraud Detection Layer

- Detect:
    - Fake location spoofing
    - Repeated abnormal claims
    - Duplicate triggers

---

## 🔹 Step 5: Auto Claim + Payout

- No manual claim needed
- Direct transfer via:
    - UPI / Wallet

---

## 🔹 Step 6: Dashboard (Deliverable Requirement)

- Weekly earnings vs losses
- Claims triggered
- Risk score trends

---

# 🧠 INTELLIGENT FRAUD DETECTION

 **“How do we ensure the delivery partner is not faking events to get payouts?”**

---

# 🚨 1. Adversarial Defense & Anti-Spoofing Strategy (FAKE LOCATION DETECTION)

## Problem:

A delivery partner may:

- Use **GPS spoofing apps**
- Fake being in a **high-risk / rain zone**
- Trigger payouts without actual disruption

---

## Detection Methods:

### 🔹 A. Speed Consistency Check

```
If distance covered / time > realistic speed → FRAUD
```

Example:

- Jump from 2 km to 10 km in 10 seconds

👉 Flag as suspicious

---

### 🔹 B. Sensor Fusion (VERY STRONG POINT)

Use:

- GPS + Accelerometer + Gyroscope

👉 If:

- GPS shows movement
- BUT accelerometer shows no motion

→ **Fake GPS**

---

### 🔹 C. Location Drift Pattern

- Real GPS → smooth movement
- Fake GPS → sudden jumps / teleportation

👉 Use:

- Standard deviation of location points

---

### 🔹 D. IP + GPS Mismatch

- GPS says: Bangalore
- IP says: Delhi

→ Fraud flag 

---

### 🔹 E. Mock Location Detection (Android)

- Check if **“Allow Mock Location”** is enabled
- Detect apps like Fake GPS

---

# 🤖 2. ANOMALY DETECTION IN CLAIMS

## ❌ Problem:

User may:

- Trigger too many claims intentionally
- Abuse system (fake cancellations, delays)

---

## ✅ Solution:

### 🔹 A. Behavioral Baseline Model

- Learn:
    - Avg failed deliveries/day
    - Avg cancellations
    - Avg delays

👉 Compare current vs normal

---

### 🔹 B. Simple Rule-Based Detection

```
IF failed deliveries > 3× normal → anomaly
```

---

### 🔹 C. ML-Based Detection (BEST)

Use:

- Isolation Forest
- One-Class SVM

Detect:

- Unusual claim patterns

---

### 🔹 D. Time-Based Suspicion

- Many claims in **short time window**

Example:

- 5 claims in 30 mins → 🚩

---

# 📍 3. LOCATION & ACTIVITY VALIDATION

## ❌ Problem:

User claims:

“I was delivering but faced issue”

But actually:

❌ Not active

❌ Not in delivery zone

---

## ✅ Validation Logic:

### 🔹 A. Active Session Check

- Was user **logged in + accepting orders?**

---

### 🔹 B. Order Matching

- Claim must match:
    - Real order ID
    - Delivery attempt logs

---

### 🔹 C. Geo-Fencing

- Check if user was:
    - Inside delivery zone
    - Near pickup/drop location

---

### 🔹 D. Time Correlation

- Claim time must match:
    - Delivery attempt timestamp

---

### 🔹 E. Call Log Validation

Example:

- “Customer not responding” claim

Check:

- ≥2–3 calls made?

If NO → reject claim

---

# 🔁 4. DUPLICATE CLAIM PREVENTION

## ❌ Problem:

User tries:

- Claiming **same event multiple times**

---

## ✅ Solutions:

### 🔹 A. Unique Event ID

Each trigger gets:

```
Event_ID = userID + timestamp + location
```

👉 Only one payout per event

---

### 🔹 B. Hash-Based Deduplication

- Store claim signature
- If repeated → reject

---

### 🔹 C. Cooldown System

```
Same type claim allowed only after X minutes
```

Example:

- Rain payout → once per hour

---

### 🔹 D. Cross-Validation

- Same event claimed by:
    - Many users → valid
- Only 1 user → suspicious

---

# 🔗 INTEGRATION CAPABILITIES

# 🌦️ 1. WEATHER APIs (Core for Environmental Triggers)

## 🔹 Purpose

Used to trigger:

- Rain payouts
- Heatwave payouts
- AQI-based disruption payouts

---

## 🔹  APIs

### 1: OpenWeatherMap

- Free tier available
- Gives:
    - Rainfall (mm/hr)
    - Temperature
    - Weather conditions

---

### 2: WeatherAPI.com

- Better for:
    - Hourly forecasts
    - Real-time conditions

---

# 🚦 2. TRAFFIC DATA

## 🔹 Purpose

Used to detect:

- Delays due to congestion
- Increased delivery time (income loss)

---

## 🔹 Api’s (planning to use)

- Google Maps Traffic API (paid)
- HERE Maps API

---

# 📦 3. PLATFORM APIs (SIMULATED )

## 🔹 Purpose

This is our **core system backbone**

Used to track:

- Orders
- Deliveries
- Cancellations
- Failed attempts

---

## 🔹 What we will Simulate

### Example Data:

```json
{
  "order_id": "ORD123",
  "status": "FAILED",
  "reason": "Customer Not Responding",
  "attempts": 3,
  "delivery_time": 25
}
```

---

## 🔹 Key Events that are Capture

- Order assigned
- Order picked
- Delivery attempt
- Cancellation
- Completion

---

## 🔹 Trigger Example

```
IF attempts ≥ 3 AND status = FAILED
→ Trigger unlucky situation payout
```

---

## 🔹 Implementation

- Use:
    - Node.js backend OR
    - Static JSON + JS simulation

---

# 💳 4. PAYMENT SYSTEM

## 🔹 Purpose

To show:

👉 **Automatic payout (VERY IMPORTANT for judges)**

---

## 🔹 Options

### 1) Razorpay

- Has **test mode**
- Can simulate payouts

---

### 2) Stripe (Global)

- Good sandbox environment

---

# FULL INTEGRATION FLOW

```
[Weather API] ─┐
[Traffic Data] ─┤
[Platform API] ─┤ → Trigger Engine → Fraud Detection → Payment System
[GPS Data] ────┘
```

---

**NOTE: “Our system integrates real-time environmental, operational, and behavioral data sources to enable automated parametric payouts without manual claims.”**

---