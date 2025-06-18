# Economic Assessment of On-Site Hydrogen Production using PEM Electrolyzer

## Project Objective

This project evaluates the economic feasibility of installing a PEM (Proton Exchange Membrane) electrolyzer to produce hydrogen on-site using real-time electricity market prices. The primary goal is to assess whether such an investment is profitable and, if so, determine the optimal size of the electrolyzer and required storage capacity.

We simulate:

- Hourly electricity prices
- A realistic hourly hydrogen demand profile
- Hydrogen production and consumption dynamics
- Economic metrics such as profit, cost savings, and payback period

Key questions addressed:

1. **Is a PEM electrolyzer economically viable under current price conditions?**
2. **What electrolyzer capacity is most appropriate for a given demand?**
3. **How much hydrogen storage is needed to meet demand peaks?**
4. **What portion of the internal demand can be covered by the system?**
5. **What annual profit and amortization period can be expected?**

---

## Final Recommendation

After testing multiple system configurations, the following setup is recommended:

- **Electrolyzer capacity:** 210 kW  
- **Hydrogen storage:** 24 kg  
- **Simulation period:** 1 year

### Simulation Summary:

| Metric                                 | Value                |
|----------------------------------------|----------------------|
| Total H₂ production                    | 39,994.59 kg         |
| Total H₂ demand                        | 42,506.00 kg         |
| Covered demand (production + storage) | 39,936.54 kg (93.9%) |
| Unmet demand                           | 2,569.46 kg          |
| Electricity cost                       | 140,972.26 €         |
| Cost savings vs. external H₂ purchase | 279,555.78 €         |
| Net annual profit                      | 244,976.14 €         |
| Amortization period                    | 1.15 years           |
| Total CAPEX (electrolyzer + storage)   | 280,800.00 €         |

This configuration covers over **93.9%** of the internal hydrogen demand and reaches **payback within just over one year**, even **without subsidies** or **external H₂ sales incentives**. Therefore, the project is considered **highly attractive** from an investment perspective.

---

## Code Structure

- `load_data()`: Preprocesses hourly electricity market prices from SMARD data
- `simulate_demand()`: Creates a synthetic hydrogen demand profile
- `production_logic()`: Decides whether to produce based on electricity prices
- `economic_calculations()`: Computes costs, savings, profits
- `storage_module()`: Simulates use of a fixed-capacity H₂ storage system
- `visualizations.py`: Plots price trends, production vs. demand, cumulative profit

---

## Next Steps: If it was a real project

- Request supplier quotations for a 210 kW PEM system and 24 kg storage
- Validate assumptions with engineering partners
- Include regulatory, maintenance, and installation costs in the financial analysis
- Evaluate the effect of fluctuating hydrogen prices and longer-term electricity trends

---

## Next Steps: Advanced Modeling with Reinforcement Learning

Based on the defined system parameters (electrolyzer size, storage capacity, electricity pricing), this project can be extended using Reinforcement Learning (RL) to build a decision-making agent that learns an optimal hydrogen operation strategy over time.

Possible RL Extensions:

    Price-aware dispatching:     Learn whether to produce, store, or sell hydrogen depending on fluctuating electricity prices and future expectations.

    Price forecasting + decision coupling:     Combine a price prediction model (e.g. time series or transformer) with a policy network to optimize decisions based on expected future prices, not just current values.

    Dynamic demand shifting:     Learn when to shift hydrogen demand (if flexible) to align better with low-cost production periods.

    Multi-agent system: 
        Extend the simulation to include:

        Grid signals (e.g. demand response)

        Competing hydrogen producers

        Variable off-take partners

    Carbon-aware operation:     Include carbon intensity of electricity in the decision logic — for cases where hydrogen must be “green by CO₂ standards.”

    Investment learning:     Use RL not just for hourly dispatch, but also to learn the best sizing of the electrolyzer and storage over time under market uncertainty.

---

## License

This project is released under the MIT License. Feel free to use, modify, and adapt for your own feasibility studies.

