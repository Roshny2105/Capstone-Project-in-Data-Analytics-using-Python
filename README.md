# NYC Airbnb Market Analysis: Pricing Dynamics & Host Behavior

An exploratory data analysis (EDA) and data cleaning project focusing on New York City's short-term rental market to uncover key pricing patterns, supply-demand distributions, and host behaviors[cite: 1].

## 📌 Project Overview
This project examines the NYC Airbnb market to explore how distinct listing attributes—such as location (boroughs), room types, and host profiles—influence pricing and booking demand[cite: 1]. Additionally, it explores market metrics to identify host listing patterns in the context of NYC's short-term rental dynamics[cite: 1].

### Key Objectives:
*   Analyze the impact of geographical location and room types on nightly pricing[cite: 1].
*   Evaluate supply and demand trends using metrics like `price`, `reviews_per_month`, and `availability_365`[cite: 1].
*   Examine host behaviors and identify multi-listing hosts using `calculated_host_listings_count`[cite: 1].
*   Perform end-to-end data processing: data cleaning, handling missing values, and outlier mitigation[cite: 1].

## 🛠️ Tools & Libraries Used
The analysis is built entirely in Python using standard data science stack libraries[cite: 1]:
*   **Pandas**: Data manipulation, loading, profiling, and cleaning[cite: 1].
*   **NumPy**: Efficient numerical operations and vectorized arrays[cite: 1].
*   **Matplotlib & Seaborn**: Statistical data visualization and exploratory plotting[cite: 1].

## 📊 Data Source
*   **Dataset**: New York City Airbnb Open Data (originally compiled from public Airbnb web-scrapes)[cite: 1].
*   **Source**: [Kaggle Dataset Link](https://www.kaggle.com/datasets/arianazmoudeh/airbnbopendata)[cite: 1].
*   **Original Scope**: Contains ~102,599 historical listings featuring 26 distinct attributes reflecting the 2019 NYC market landscape[cite: 1].

### Methodology Note:
To ensure notebook optimization and efficient chart generation, a statistically rigorous **stratified random sample of 5,000 listings** was extracted[cite: 1]. This sampling strategy preserves the overall distribution ratios of `neighbourhood_group` and `room_type` found in the parent dataset[cite: 1].

## 🗂️ Data Attributes
The project processes 16 key structural columns out of the raw records, including[cite: 1]:
*   `id` / `NAME`: Unique listing identifiers and titles[cite: 1].
*   `host_id` / `host_name`: Unique host credentials[cite: 1].
*   `neighbourhood_group`: Broad NYC boroughs (*Manhattan, Brooklyn, Queens, Bronx, Staten Island*)[cite: 1].
*   `neighbourhood`: Specific sub-neighborhood locations[cite: 1].
*   `room_type`: Accommodation style (*Entire home/apt, Private room, Shared room*)[cite: 1].
*   `price` / `service_fee`: Continuous financial listing metrics[cite: 1].
*   `minimum_nights` / `availability_365`: Booking restrictions and operational availability[cite: 1].
*   `number_of_reviews` / `reviews_per_month`: Proxy metrics tracking historical demand[cite: 1].

## 🚀 Data Processing Workflow
1.  **Initial Overview**: Loading raw CSV, querying `.info()`, profiling structural missing percentages, and assessing data types[cite: 1].
2.  **Stratification**: Sampling a representative target segment (5,000 records) to mitigate localized memory latency[cite: 1].
3.  **Feature Pruning**: Removing sparse and irrelevant features (e.g., dropping the `license` column due to high null density)[cite: 1].
4.  **Data Cleaning & Typing**: Systematically parsing messy financial text parameters (`$100`) into clean operational floats for descriptive visualization[cite: 1].

## 📈 Key Insights & Results
This analysis of 5000 NYC Airbnb listings reveals the market is professionalizing, yet Individual hosts remain competitive on satisfaction metrics.

**Key Findings:**

**1. Market Structure & Supply**  
Approximately 37% of listings are operated by Commercial hosts, while 63% are Individuals. Despite being fewer in number, Commercial hosts control disproportionate inventory due to 60% higher average availability 177 vs 111 days. Manhattan dominates the luxury segment, while Bronx and Queens serve budget demand.

**2. Pricing & Demand Dynamics**  
NET RATE shows only 7.5% spread across boroughs, from Brooklyn $654.60 to Staten Island $608.70, indicating borough location explains less variance than room type and host strategy. Room-type logic breaks in NYC: Entire home/apt $646.53 is priced nearly identical to Private room $643.71, while Shared rooms $660.15 command a scarcity premium. Price and reviews_per_month show weak negative correlation, suggesting higher price reduces booking frequency.

**3. Trust, Verification & Risk**  
Verification status has minimal impact on guest satisfaction, with Review Rate Number flat at 3.29 across Verified, Unconfirmed, and Unknown hosts. However, "Unknown" hosts price 24% higher $798.67 but maintain 46% lower availability 73 vs 136 days, indicating new hosts overprice before market learning. Approximately {risky_pct}% of listings are flagged with `illegal_risk_score >= 1` due to short-term Entire home rentals without license, highlighting Local Law 18 compliance risk concentrated in Manhattan and Brooklyn.

**Strategic Implication:**  
NYC Airbnb pricing power derives from `Room Type + Location combo` and `Availability 365`, not borough name or verification badge. For hosts, maximizing calendar availability and listing Entire homes in high-demand Brooklyn neighborhoods drives revenue. For guests, value lies in Private rooms in outer boroughs with verified hosts. For the platform, monitoring high-risk listings is critical for regulatory compliance.

**Limitation:**  
Dataset lacks `year_of_construction` and `license` details. Future analysis incorporating building age and legal licensing data would strengthen risk assessment accuracy.
