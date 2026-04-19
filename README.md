# Tree Huggers: Scaling Nature-Based Solutions with AI
**Hack for Tokyo: AI x Sustainability Hackathon - Track B (Green Carbon)**

![Agreen Connect Ledger](agreen_interactive_ledger.html) *(See interactive map in repo)*

## 🌍 The Vision
Green Carbon’s immediate challenge is reconciling unstructured farmer records (spreadsheets) with unaligned spatial data (KMZ polygons) in Japanese rice paddies. 

**Our solution solves this today, but is built for tomorrow.** In the Brazilian Amazon, land tenure is the single biggest hurdle to climate finance. By automating the reconciliation of local community records with satellite polygons, our engine creates an auditable "Geospatial Ledger." This unlocks billion-dollar carbon markets for indigenous and local smallholders by definitively proving land stewardship.

## ⚠️ The Problem
Simple area-matching algorithms fail because:
1. **Area Noise:** Farmers estimate land size with human error. 
2. **Ambiguity:** In large regions, multiple farms share identical area sizes, causing duplicate matches.
3. **Static Logic:** Hard-coded logic fails to generalize across different topographies.

## 🚀 Our Technical Approach
We built a dynamic, self-correcting machine learning pipeline:

1. **Threshold Optimization (Epsilon):** We trained a model directly on Green Carbon's area distribution to find the statistically optimal error threshold ($\epsilon$ = 0.2460 ha). This maximizes the F1-Score, ensuring we capture real "Signal" (Matches) while filtering out the "Noise" (Mismatches).
2. **Bipartite Graph Matching:** We deployed the **Hungarian Algorithm** to evaluate the entire dataset globally. Instead of guessing farm-by-farm, it finds the mathematically optimal 1-to-1 pairing that minimizes the total global error margin.
3. **Interactive Ledger:** A Kepler.gl spatial dashboard that visualizes the AI's confidence, flagging conflicts (Red) and auto-approving verified matches (Green) for carbon credits.

## 🔮 Future Roadmap: Agreen Connect
* **Interactive Feedback Loop:** Field agents and farmers can suggest boundary switches via a mobile web app.
* **Neighbor Consensus:** If a farmer claims a boundary shift, the system automatically checks with the neighboring farmer's app for consensus before updating the ledger.
* **Vision Transformers:** Integration of SAM (Segment Anything Model) to auto-detect tree-lines and crop boundaries from satellite tiles when text data fails.

## 💻 How to Run Locally

### Prerequisites
Ensure you have Python 3.8+ installed. Install the required dependencies:
```bash
pip install pandas numpy scikit-learn geopandas keplergl matplotlib seaborn