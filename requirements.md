Kisan Drishti – Requirements Specification
1. Problem Statement

    In Bharat, crop loss is rarely caused by the absence of solutions — it is caused by the absence of timely, trustworthy information.

    Small and marginal farmers lack immediate access to plant pathologists or agri-extension services. As a result:

    Panic-Driven Chemical Usage: In the absence of accurate diagnosis, farmers indiscriminately apply pesticides, degrading soil health, increasing input costs, and accelerating long-term yield decline.

    Delayed Expert Intervention: In remote regions such as Vidarbha, Bundelkhand, or interior Punjab, physical expert visits often arrive after irreversible crop damage has already occurred.

    Silent Disease Spread: Crop diseases propagate across villages undetected due to the lack of real-time surveillance mechanisms.

    Economic Loss at Scale: India incurs an estimated ₹50,000+ Crore annual loss due to preventable crop diseases and pest infestations.

    There exists a critical gap for a real-time, field-deployable, and vernacular-first crop health intelligence system tailored to the realities of rural India.

2. Target Users
Primary Users

    Small & Marginal Farmers
    Farmers operating under tight margins who require instant, voice-assisted, low-bandwidth diagnosis on affordable Android devices.

Secondary Users

    Agricultural Extension Officers
    District-level officers who require data-driven visibility into emerging disease hotspots for proactive intervention.

    Farmer Producer Organizations (FPOs)
    Organizations managing collective crop health across multiple villages and crop cycles.

3. Core Functional Requirements
3.1 Vision-Based Crop Disease Diagnosis

    AI-powered image recognition capable of identifying 30+ crop-specific diseases (e.g., Paddy Blast, Wheat Rust, Leaf Curl).

    Confidence-scored diagnosis to guide treatment reliability.

3.2 Community-Level Disease Intelligence

    Anonymized diagnostic data contributes to village and district-level disease heatmaps.

    Early-warning alerts notify nearby farmers of potential outbreaks before visible symptoms emerge.

3.3 Vernacular & Voice-First Interaction

    End-to-end voice support (input + output) in Hindi, Tamil, Telugu, and Punjabi.

    Designed for low-literacy users with minimal text dependency.

3.4 Precision Treatment & Dosage Guidance

    Crop-stage and acreage-aware dosage calculators to prevent chemical overuse.

    Rmmendations include cost-effective and locally available treatments, including organic alternatives.

3.5 Offline-First System Design

    On-device edge inference enables diagnosis in 2G or zero-connectivity environments.

    Automatic data synchronization when connectivity is restored.

3.6 Local Market Connectivity

    Integration with nearby verified agri-input dealers to ensure timely access to recommended solutions.

4. Non-Functional Constraints
4.1 Device & Hardware Constraints

    Must perform reliably on low-end Android smartphones (≥3GB RAM) commonly used in rural regions.

4.2 Connectivity Constraints

    Designed for high-latency, intermittent networks, prioritizing graceful degradation over failure.

4.3 Data Quality Constraints

    Robust handling of blurry, low-light, and partially occluded images captured under field conditions.

4.4 Privacy & Trust

    Farmer data must remain anonymized, with location data aggregated only at the community level.

5. Success Metrics & Evaluation Criteria
Technical Metrics

   1.Model Performance: Maintain an F1-score ≥ 92% across top 10 Indian cash crops.
   2.Latency: Deliver diagnosis results in ≤ 3 seconds on a standard 4G network.

Behavioral & Economic Impact

    1.Adoption: Achieve ≥ 60% weekly active usage among pilot farmers during crop seasons.

    2.Cost Reduction: Reduce pesticide expenditure by ≥ 15% for participating farmers.

    3.Early Intervention: Detect disease clusters at least 7 days earlier than traditional reporting mechanisms.

6. Outcome Vision

   1.Kisan Drishti shifts crop disease management in India from reactive damage   control to proactive prevention, empowering farmers with instant intelligence 
   2.while enabling authorities to act on real-time field data.
   The goal is not merely to diagnose a sick plant — but to prevent an entire village’s harvest from failing.