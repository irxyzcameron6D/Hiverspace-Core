*This document is the technical specification for the Joule-Dollar system.*
*For the conceptual foundation and the political case for energy-backed*
*currency see `joule-dollar-protocol.md`*

# THE JOULE-DOLLAR SPECIFICATION
## A Thermodynamically Anchored Currency for a Planetary Civilization

*Version 1.0 — Technical Specification*
*Open Source — Subject to revision by the Swarm*

---

> *"Every fiat currency in history has failed.*
> *Every currency anchored to physical reality has survived*
> *as long as the physical reality it was anchored to survived.*
> *The Joule-Dollar is anchored to the most fundamental*
> *physical reality available: energy itself.*
> *The second law is the central bank.*
> *It has never failed. It never will."*

---

## EXECUTIVE SUMMARY

The Joule-Dollar (J$) is a cryptographic currency mathematically pegged to verified physical energy generation. It cannot be printed. It cannot be inflated by political decision. It cannot be manipulated by central banks serving factional interests. Its value is determined by the laws of thermodynamics rather than by the political decisions of dominant factions.

One Joule-Dollar represents one verified unit of clean energy generated and recorded on the Swarm ledger. The currency is minted only when energy is actually produced. It is distributed according to mathematically specified rules encoded in immutable smart contracts. It is the financial instrument that makes the Dynamic Homeostatic Baseline possible, the Housing Liberation Cascade operable, and the direct production-distribution system functional.

This document specifies the technical architecture of the Joule-Dollar system — the Proof-of-Generation mechanism, the minting protocol, the distribution rules, the DHB smart contract, and the governance framework that prevents any faction from capturing the currency system for private advantage.

---

## SECTION 1 — THE PROBLEM WITH FIAT CURRENCY

### 1.1 The Thermodynamic Failure of Fiat Money

All fiat currencies share a single structural vulnerability: their value is determined by political decision rather than by physical constraint. A central bank can create money by changing a number in a ledger. There is no physical limit on this creation. The only constraint is political — the restraint of the institutions controlling the currency.

Political constraints fail. They fail because dominant factions have both the incentive and the capacity to pressure currency-issuing institutions in directions that serve factional rather than system-wide interests. Inflation is not primarily a monetary phenomenon. It is a thermodynamic one — the signal that energy is being consumed faster than it is being produced, or that the labeling system has decoupled from the physical reality it is supposed to represent.

**The thermodynamic statement of the fiat currency problem:**

Fiat currency violates the first law of thermodynamics as applied to economic systems. The first law states that energy cannot be created from nothing. Fiat currency creation is the economic equivalent of claiming to create energy from nothing — it creates a claim on real goods and services without creating the real goods and services that claim represents. The result is the thermodynamic equivalent of entropy generation — the degradation of the currency's ability to accurately represent the productive capacity of the system.

### 1.2 Historical Currency Anchors and Their Failures

Every previous attempt to anchor currency to physical reality has eventually failed — not because the principle was wrong but because the anchor was chosen incorrectly.

**The Gold Standard** anchored currency to a specific element whose supply was determined by geological accident rather than productive capacity. Gold production has no systematic relationship to the productive output of the economies using it as an anchor. When gold supply grew faster than productive output, inflation resulted. When it grew slower, deflation resulted. The anchor was real but arbitrary.

**Commodity Standards** anchored currency to specific commodities — oil, grain, metals. These suffered the same problem as gold: the anchor commodity's supply had no systematic relationship to the overall productive capacity of the economy.

**The Correct Anchor:** Energy. Not a specific form of energy — not oil, not gold, not any commodity — but **verified energy generation itself**. Energy is the universal input to all productive activity. Nothing is produced without energy. The total productive capacity of any economy is a function of the energy available to it and the efficiency with which that energy is converted to useful work. A currency anchored to verified energy generation is anchored to the most fundamental physical quantity underlying all economic activity.

### 1.3 Why Clean Energy Specifically

The Joule-Dollar is pegged to **clean energy generation** — solar, wind, geothermal, fusion, and other non-depleting sources — rather than to total energy generation including fossil fuels.

The reason is thermodynamic. Fossil fuel energy is extracted from a finite stock — the degraded remains of biological material accumulated over hundreds of millions of years. Its extraction generates entropy not only in the conversion process but in the atmospheric loading of combustion products that destabilize the planetary steady state. A currency anchored to fossil fuel extraction is a currency that rewards the depletion of a finite resource and the generation of long-term ecological stress.

Clean energy generation is a flow rather than a stock. The sun delivers approximately 173,000 terawatts to the Earth's surface continuously. Wind, geothermal, and tidal forces add additional continuous flows. A currency anchored to the capture of these flows is a currency that rewards the expansion of productive capacity without depleting the resource base. **It is the first currency in history whose expansion is thermodynamically aligned with the long-term survival of the civilization using it.**

---

## SECTION 2 — THE PROOF-OF-GENERATION MECHANISM

### 2.1 Overview

The Proof-of-Generation (PoG) mechanism is the technical foundation of the Joule-Dollar. It is the system by which clean energy generation is verified, recorded on the Swarm ledger, and converted into J$ at a specified exchange rate.

The PoG mechanism must satisfy four requirements:

1. **Verifiability** — Energy generation must be independently verifiable. No single actor can falsify generation data.
2. **Tamper-resistance** — Once recorded, generation data cannot be altered retroactively.
3. **Accessibility** — Any energy-generating node anywhere on the planet must be able to participate.
4. **Scalability** — The system must be able to handle energy generation data from billions of nodes simultaneously.

### 2.2 The Hardware Layer — Generation Meters

Every energy-generating installation participating in the Joule-Dollar system is equipped with a **Generation Meter (GM)** — a tamper-evident hardware device that:

- Measures energy output in real time with calibrated precision
- Generates cryptographically signed data packets at specified intervals (default: every 15 minutes)
- Transmits data packets to the Swarm ledger via encrypted connection
- Maintains a local encrypted record of all generation data as a backup
- Cannot be reset, overridden, or tampered with without generating a cryptographic alert

The GM hardware specification is open source. Any manufacturer can produce certified GMs. Certification requires passing a standardized testing protocol administered by the Swarm's technical verification nodes. No single manufacturer can capture the GM market — the specification is public and the certification process is distributed.

### 2.3 The Verification Layer — Node Consensus

Raw generation data from individual GMs is verified through a distributed consensus mechanism involving multiple independent verification nodes before being recorded on the Swarm ledger.

**Verification process:**

```
Step 1: GM generates signed data packet
        {timestamp, location_id, generation_kwh, device_signature}

Step 2: Packet transmitted to minimum 7 verification nodes
        (selected randomly from active verification pool)

Step 3: Verification nodes cross-reference:
        - Device signature against registered GM registry
        - Generation data against meteorological data
          (solar irradiance, wind speed) for location
        - Generation data against historical baseline
          for device type and location
        - Timestamp against network time protocol

Step 4: If 5 of 7 nodes confirm validity:
        Data recorded on Swarm ledger as VERIFIED
        J$ minted according to exchange rate schedule

Step 5: If consensus not achieved:
        Flagged for human review by technical committee
        Generation paused pending investigation
```

**Anti-fraud measures:**

- Meteorological cross-referencing prevents false generation claims (a solar panel cannot generate power during a documented cloudy day at that location)
- Historical baseline comparison flags anomalous generation spikes
- Device signature verification prevents spoofed meter data
- Random verification node selection prevents collusion

### 2.4 The Exchange Rate — Joules to J$

The exchange rate between physical energy generation and J$ is the most critical parameter in the system. It must be set to:

1. Make clean energy generation economically rewarding at every scale from household solar to utility installations
2. Prevent the currency supply from expanding faster than the system's productive capacity
3. Automatically adjust as global clean energy generation capacity changes

**The base exchange rate:**

```
1 J$ = 1 kilowatt-hour (kWh) of verified clean energy generation

This is the fundamental unit. All other exchange calculations
derive from this base rate.
```

**Rationale for this rate:**

One kilowatt-hour is a meaningful quantity of energy — it is roughly the amount of energy required to run a typical household refrigerator for a day, or to charge an electric vehicle for approximately 3 miles of range. It is large enough to be meaningful but small enough to be achievable by small-scale generators. At typical solar panel output rates, a modest 5kW residential installation generates approximately 20 kWh per day — 20 J$ per day or approximately 7,300 J$ per year. This is a meaningful economic quantity for a household-scale generator.

**The Dynamic Adjustment Mechanism:**

As global clean energy generation capacity expands, the J$ supply will expand proportionally. To prevent the currency from inflating as generation capacity grows, the exchange rate includes a **productivity adjustment factor** (PAF):

```
Effective Exchange Rate = Base Rate × PAF

PAF = (Global Productive Output Index at time t) /
      (Global Productive Output Index at base year)

where Global Productive Output Index measures the total
useful work produced by the global economy per unit time.
```

This ensures that J$ supply grows in proportion to actual productive capacity rather than simply in proportion to energy generation. If energy generation doubles but productive output only increases by 50%, the exchange rate adjusts so that the J$ supply increases by 50% rather than 100%.

The PAF calculation is performed by the Swarm's economic monitoring nodes using open data sources and published methodology. The calculation is auditable by any node with sufficient technical capacity.

---

## SECTION 3 — THE MINTING PROTOCOL

### 3.1 How J$ Are Created

J$ are created through one mechanism only: **verified clean energy generation recorded on the Swarm ledger**. There is no other minting mechanism. No central bank. No quantitative easing. No political decision-making authority over currency supply. The minting protocol is encoded in the Swarm ledger's smart contract layer and cannot be altered except through the Swarm's governance process (Stochastic Sortition with supermajority threshold).

**The minting sequence:**

```
1. GM records verified generation event
2. Verification nodes achieve consensus
3. Ledger smart contract calculates J$ to mint:
   
   J$_minted = kWh_verified × (1 / PAF)

4. J$ allocated according to distribution protocol:
   - 70% → Generator wallet (reward for generation)
   - 15% → DHB pool (automatic baseline distribution)
   - 10% → Swarm capital pool (planetary projects)
   - 5%  → Verification node compensation

5. Transaction recorded on ledger as immutable entry
6. Generator receives J$ in real time
```

### 3.2 The Generator Reward

The generator — whether a household with rooftop solar, a community wind cooperative, or a utility-scale clean energy installation — receives 70% of all J$ minted from their verified generation.

This reward structure is designed to incentivize maximum clean energy generation at every scale. A household that installs solar panels is not just reducing its electricity bill — it is generating currency. A community that builds a wind cooperative is not just generating local employment — it is minting money. The generator is the central actor in the J$ economy. The currency rewards what the planet needs: the maximum possible generation of clean energy from all available sources.

**Generator wallet:** Each registered generating installation has a unique cryptographic wallet address. J$ flow directly to this address upon minting. The generator can hold J$, spend J$, or convert J$ to other currencies through the Swarm's exchange mechanism. No intermediary touches the generator's J$ between minting and the generator's wallet.

### 3.3 The DHB Pool

15% of all J$ minted flows automatically to the Dynamic Homeostatic Baseline pool — the fund from which the unconditional survival floor is distributed to every registered living node on the planet.

This is not taxation. It is the thermodynamic recognition that energy generation is a social activity — that the infrastructure, education, legal system, and social stability that make energy generation possible are collective products. The DHB allocation is the generator's automatic contribution to maintaining the conditions that make generation possible.

The DHB pool is governed by an immutable smart contract that calculates the per-node distribution daily based on:

```
DHB_per_node = DHB_pool_balance / registered_living_nodes

Distributed automatically to every registered node's wallet
at 00:00 UTC daily.

Cannot be reduced below the E(min) threshold.
Cannot be withheld from any registered living node
for any reason including debt, criminal conviction,
or political status.
```

### 3.4 The Swarm Capital Pool

10% of all J$ minted flows to the Swarm Capital Pool — the fund from which planetary-scale projects are financed. Vertical farms. Antibiotic research. Reforestation. Space defense infrastructure. The communication satellite network. Aquafarming. Wildlife migration corridors.

The allocation of Swarm Capital Pool funds is determined by the Swarm's governance process — Stochastic Sortition with directed taxation preferences expressed by registered nodes. No individual, corporation, or government controls the Swarm Capital Pool. It is governed by the collective expressed preferences of the nodes that generate the energy that funds it.

### 3.5 Verification Node Compensation

5% of all J$ minted flows to the verification nodes that confirmed the generation event. This compensation is distributed equally among the seven verification nodes that participated in the consensus process.

Verification node compensation serves two functions. It incentivizes participation in the verification network — nodes that perform verification work are compensated for that work. And it decentralizes the verification function — any node with sufficient technical capacity can become a verification node and earn J$ for performing the verification work that keeps the currency honest.

---

## SECTION 4 — THE DHB SMART CONTRACT

### 4.1 Contract Specification

The Dynamic Homeostatic Baseline is implemented as an immutable smart contract on the Swarm ledger. Its core logic cannot be altered by any actor — not by the Swarm's governance process, not by any government, not by any corporation, not by the original designers of the system.

**The DHB contract guarantees:**

```solidity
// Pseudocode representation of DHB core logic

contract DynamicHomeostaticBaseline {
    
    // The absolute floor — cannot be set below this value
    // regardless of any other calculation
    uint256 constant ABSOLUTE_FLOOR = E_MIN_JOULES_PER_DAY;
    
    // No authority can override this function
    function distributeDaily() external {
        uint256 pool_balance = DHB_pool.balance;
        uint256 node_count = registry.livingNodeCount();
        uint256 per_node = pool_balance / node_count;
        
        // Enforce absolute floor
        if (per_node < ABSOLUTE_FLOOR) {
            per_node = ABSOLUTE_FLOOR;
            // Deficit covered by Swarm Capital Pool emergency reserve
        }
        
        // Distribute to every registered living node
        for (address node : registry.allLivingNodes()) {
            node.wallet.transfer(per_node);
        }
        
        // This function cannot be paused, modified, or overridden
        // by any external call, governance decision, or emergency declaration
    }
    
    // Conditions that CANNOT affect distribution:
    // - Node's criminal record
    // - Node's political affiliation
    // - Node's debt status
    // - Node's location
    // - Government request
    // - Court order
    // - Emergency declaration
    // The DHB is unconditional. Period.
}
```

### 4.2 The E(min) Calculation

E(min) — the minimum energy for homeostasis — is calculated based on verified scientific data and updated annually by the Swarm's scientific advisory nodes using open methodology.

**Current E(min) components:**

| Component | Daily Requirement | J$ Equivalent |
|-----------|------------------|---------------|
| Biological Fuel (Nutrition) | ~10 Megajoules (~2,400 kcal) | ~2.78 J$ |
| Thermal Regulation (Shelter/HVAC) | ~5–15 kWh depending on climate | ~5–15 J$ |
| Cellular Maintenance (Healthcare access) | Actuarial calculation per node | Variable |
| Communication access | ~0.1 kWh | ~0.1 J$ |
| **Total E(min) — temperate climate** | | **~10–20 J$/day** |

E(min) is **localized** — it varies by climate, geographic location, and local cost of essential goods. A node in a tropical climate has lower thermal regulation costs than a node in a subarctic environment. The DHB contract calculates localized E(min) using:

```
E(min)_local = Base_E(min) × Climate_Factor × Local_Cost_Index

Climate_Factor = function(average_temperature, temperature_variance)
Local_Cost_Index = function(local_price_level, supply_chain_accessibility)
```

Both factors are calculated from open data sources updated monthly and auditable by any node.

### 4.3 Node Registration

Every living human node is eligible for DHB distribution upon registration on the Swarm ledger. Registration requires:

- **Proof of biological existence:** Biometric verification (fingerprint, iris scan, or equivalent) that the registering entity is a living human being
- **Proof of uniqueness:** Cryptographic verification that this biological entity has not previously registered (prevents duplicate registrations)
- **Location declaration:** Self-reported location for E(min) localization calculation (not used for any other purpose, not shared with any government)

Registration is free. Registration is permanent — a registered node remains registered until biological death is verified. Registration cannot be revoked by any government, court, or governance body.

**Privacy:** The Swarm ledger records only the cryptographic hash of biometric data — not the biometric data itself. The mapping between a node's biological identity and their wallet address is stored only in their personal device. The Swarm cannot identify which wallet belongs to which person. Only the node knows this mapping.

---

## SECTION 5 — CURRENCY EXCHANGE AND INTEGRATION

### 5.1 Exchange with Legacy Currencies

The Joule-Dollar is not designed to immediately replace legacy currencies. It is designed to provide an alternative — a thermodynamically honest currency that operates in parallel with existing systems and gradually captures an increasing share of economic activity as its advantages become apparent.

**The Swarm Exchange:** A decentralized exchange mechanism allows nodes to convert J$ to and from legacy currencies at market-determined rates. The exchange:

- Is fully decentralized — no single entity controls it
- Uses automated market-making algorithms with parameters set by Swarm governance
- Charges a 0.1% transaction fee that flows to the Swarm Capital Pool
- Operates 24/7 with no restrictions on conversion volume
- Cannot be shut down by any government or regulatory body

**Exchange rate dynamics:** The J$ exchange rate with legacy currencies will be determined by the market — by the supply of J$ (which grows with clean energy generation) and the demand for J$ (which grows with the expansion of the Swarm economy). As the Swarm economy grows and more goods and services are priced in J$, demand for J$ will increase. As clean energy generation capacity expands, J$ supply will increase. The exchange rate will reflect the market's assessment of the relative thermodynamic efficiency of the two currency systems.

### 5.2 The Direct Production Integration

The Joule-Dollar is the native currency of the Hiverspace direct production-distribution system. When nodes aggregate demand for a product or service, they express that demand in J$. When manufacturers submit offers to the aggregated demand pool, they price those offers in J$. All transactions in the direct production system are settled in J$.

This integration creates a virtuous cycle: nodes that generate clean energy earn J$, which they use to purchase goods and services through the direct production system, which incentivizes manufacturers to accept J$, which incentivizes more nodes to generate clean energy to earn J$.

### 5.3 The Housing Liberation Integration

The Housing Liberation Cascade operates entirely in J$. The founding ten million nodes contribute 10 J$ per month to the housing fund. Mortgages are purchased in J$. Freed nodes contribute 100 J$ per month. The entire cascade — from the first contribution to the freeing of the four billionth node — runs on the Swarm ledger in J$.

This integration means that every node freed from rent is simultaneously a node that has participated in the J$ economy — that has experienced the currency as something that delivers real value in their real life. The freed node is the most powerful advertisement for the J$ system that exists. They are living proof that the currency works.

---

## SECTION 6 — GOVERNANCE AND ANTI-CAPTURE MECHANISMS

### 6.1 The Fundamental Governance Principle

The Joule-Dollar system is designed to be uncapturable by any faction — including the Swarm itself. The mechanisms that protect the currency from capture are structural, not political. They are encoded in the smart contract layer and cannot be overridden by governance decisions.

**What governance CAN do:**
- Adjust the PAF calculation methodology (with supermajority threshold)
- Add new categories of clean energy to the eligible generation list
- Modify the verification node selection algorithm
- Adjust the distribution percentages within specified ranges
- Approve new GM hardware specifications

**What governance CANNOT do:**
- Reduce the DHB below E(min) for any node
- Create J$ through any mechanism other than Proof-of-Generation
- Grant any node, government, or organization privileged access to the minting process
- Retroactively alter recorded transactions
- Exclude any registered living node from DHB distribution

### 6.2 The 15% Collective Ownership Limit

The Swarm's collective investment trust — which accumulates J$ through the Swarm Capital Pool — cannot acquire more than 15% of the outstanding voting shares of any single corporation. This limit is hardcoded into the Swarm's investment smart contracts and cannot be overridden by any governance vote.

This limit preserves the market independence of corporations serving the Swarm while giving the Swarm sufficient ownership to demand transparency and accountability. The Swarm has voice. It does not have control. Voice is what it needs. Control is what it must never become.

### 6.3 The Mandatory Efficiency Audit

Every allocation from the Swarm Capital Pool undergoes a mandatory efficiency audit before funds are released. The audit is performed by the Swarm's AI adjudication layer using the Rosetta Key framework:

```
Audit criteria:
1. Does this allocation move more nodes above E(min)?
2. Does it increase system efficiency η?
3. Does it reduce the Entropy Generation Index?
4. Does it pass the Village Well Assessment?
   (What other functions does the system being
   replaced currently perform?)
5. Does it serve the Swarm's thermodynamic interest
   or a faction's financial interest?

If the allocation fails any criterion:
- Flagged for human review by randomly selected 
  governance nodes
- Released only with explicit governance approval
  documenting the reasoning for the exception
```

### 6.4 The Anti-Inflation Guarantee

The Joule-Dollar system includes three structural anti-inflation guarantees:

**Guarantee 1 — No printing:** J$ can only be created through verified energy generation. There is no mechanism by which J$ can be created without corresponding physical energy generation.

**Guarantee 2 — The PAF adjustment:** The productivity adjustment factor ensures that J$ supply grows in proportion to productive capacity, not simply in proportion to energy generation.

**Guarantee 3 — The velocity cap:** Smart contracts limit the rate at which J$ can flow through the economy, preventing speculative velocity spirals that can cause inflation in conventional currencies.

---

## SECTION 7 — IMPLEMENTATION ROADMAP

### Phase 1 — Alpha Node (Months 1–12)

**Objective:** Demonstrate technical feasibility at small scale.

- Deploy Swarm ledger on distributed node network (minimum 1,000 nodes)
- Manufacture and certify first batch of Generation Meters (target: 10,000 units)
- Deploy DHB smart contract in test environment
- Register first 100,000 nodes
- Begin J$ minting from registered generation installations
- First DHB distributions to registered nodes
- Open source all code, hardware specifications, and methodology

**Success metric:** System operates for 12 months without security breach, with verified generation data from 10,000 registered installations, and DHB distributions reaching 100,000 nodes.

### Phase 2 — Cascade Ignition (Months 12–36)

**Objective:** Launch the Housing Liberation Cascade and establish J$ as a functional currency.

- Housing Liberation Fund smart contract deployed
- First 10 million founding nodes recruited
- First mortgage purchases executed
- Direct production platform launched in pilot markets
- J$ exchange with legacy currencies operational
- Target: 1 million nodes freed from rent

**Success metric:** 1 million nodes freed. J$ accepted by minimum 10,000 merchants and service providers. Exchange rate stable within 20% band over 6-month period.

### Phase 3 — Cascade Acceleration (Months 36–84)

**Objective:** Achieve thermodynamic tipping point — 100 million freed nodes.

- Swarm communication satellite network Phase 1 deployed
- Vertical farm pilot programs operational in 10 cities
- Global Health Trust launched
- Education Credits system piloted in 5 jurisdictions
- Stochastic Sortition governance operational in pilot communities

**Success metric:** 100 million nodes freed from rent. J$ accepted as primary currency by Swarm nodes. Clean energy generation capacity increased by minimum 10% attributable to J$ incentives.

### Phase 4 — Planetary Integration (Months 84–144)

**Objective:** 4 billion nodes freed. J$ established as significant global currency.

- Full satellite network operational
- DHB reaching all registered nodes above E(min)
- Direct production system handling significant fraction of global consumer goods
- Global Health Trust operational globally
- Planetary Emergency Energy Fund operational

**Success metric:** 4 billion nodes above E(min). J$ exchange rate stable. Clean energy generation representing majority of new capacity additions globally.

---

## SECTION 8 — WHAT THE ENGINEERS NEED TO BUILD

This section is addressed directly to the software engineers, cryptographers, and hardware engineers who will build the Joule-Dollar system.

### The Ledger

The Swarm ledger is a distributed ledger with the following requirements:

- **Throughput:** Minimum 100,000 transactions per second (scaling to 10 million as adoption grows)
- **Finality:** Transactions confirmed within 15 seconds
- **Energy efficiency:** The ledger's own energy consumption must be a small fraction of the energy it is recording — proof-of-stake or equivalent, not proof-of-work
- **Open source:** All code publicly auditable
- **Forkable:** Any node can fork the ledger if they believe the main chain has been compromised — but the DHB guarantee follows the main chain with the majority of registered nodes

### The Smart Contracts

Priority contracts for initial deployment:

1. **DHB Distribution Contract** — Daily distribution to all registered nodes. Immutable core logic. Adjustable parameters within specified ranges.

2. **Minting Contract** — Creates J$ upon verified generation. Distributes according to specified percentages. Immutable allocation rules.

3. **Housing Liberation Contract** — Accepts 10 J$/month contributions. Executes mortgage purchases according to lottery protocol. Manages freed node contribution tracking.

4. **Verification Node Contract** — Manages verification node registration, selection, consensus recording, and compensation.

5. **Swarm Capital Allocation Contract** — Receives 10% of minted J$. Distributes according to governance-expressed preferences. Enforces efficiency audit requirements.

### The Generation Meter

Hardware requirements for the Generation Meter:

- Tamper-evident physical enclosure with cryptographic alert on breach
- Calibrated energy measurement accurate to ±0.5%
- Cryptographic signing of all data packets using device-unique key
- Encrypted transmission to verification nodes
- Local encrypted backup of all generation data
- Operating temperature range: -40°C to +85°C
- Expected operational lifespan: minimum 25 years
- Open hardware specification — any manufacturer can produce certified units

### The Mobile Wallet

Every registered node needs a secure mobile wallet for:

- Receiving DHB distributions
- Spending J$ for goods and services
- Contributing to the Housing Liberation Fund
- Expressing direct taxation preferences
- Participating in Swarm governance

The wallet must work on low-cost Android devices in areas with limited connectivity. Offline functionality is essential — many registered nodes will be in areas without reliable internet access. The wallet syncs when connectivity is available and queues transactions for execution when the connection is restored.

---

## CONCLUSION — THE CURRENCY THE SECOND LAW WOULD DESIGN

If the second law of thermodynamics could design a currency it would design the Joule-Dollar.

It would anchor the currency to verified energy generation — because energy is the universal input to all productive activity. It would distribute a baseline to every living node — because a system in which nodes fall below E(min) is a system generating entropy faster than it generates useful work. It would make the currency supply grow with productive capacity — because a currency that grows faster than productive capacity is a currency generating thermodynamic noise. It would make the system uncapturable by any faction — because faction capture is the primary source of thermodynamic inefficiency in social systems.

The Joule-Dollar is not a utopian currency. It does not promise that everything will be fine. It promises that the financial system will for the first time in human history be aligned with physical reality rather than opposed to it. That the nodes who generate the energy that powers civilization will be compensated for that generation. That the nodes who cannot yet generate — the children, the elderly, the disabled, the temporarily displaced — will receive the thermodynamic floor they need to maintain biological steady state.

That the second law will be the central bank.

And the second law has never failed.

---

## REFERENCE — KEY PARAMETERS

| Parameter | Value | Governance |
|-----------|-------|------------|
| Base exchange rate | 1 J$ = 1 kWh verified clean generation | Immutable |
| Generator allocation | 70% of minted J$ | Adjustable ±10% by supermajority |
| DHB pool allocation | 15% of minted J$ | Adjustable ±5% by supermajority |
| Swarm capital allocation | 10% of minted J$ | Adjustable ±5% by supermajority |
| Verification compensation | 5% of minted J$ | Adjustable ±2% by supermajority |
| Verification consensus threshold | 5 of 7 nodes | Adjustable 4–6 by supermajority |
| DHB distribution frequency | Daily | Immutable |
| Maximum collective ownership | 15% per corporation | Immutable |
| Efficiency audit requirement | All Swarm Capital allocations | Immutable |
| DHB unconditional guarantee | No conditions permitted | Immutable |

---

*Hiverspace — The Joule-Dollar Specification — Version 1.0*
*Open Source — All Nodes — No Factions — No Waste*
*The second law is the central bank.*
*Built on the General Theory of Social Behavior — original work circa 1990*
*Subject to revision by the Swarm and the engineering community*
