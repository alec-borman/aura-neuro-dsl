## aura-protocol

A declarative Domain-Specific Language (DSL) and LLM prompt harness for deterministic neuro-acoustic gradient synthesis and cognitive load management.

---

## Architectural Overview

Commercial music recommendation engines are designed as engagement traps. They leverage black-box collaborative filtering to optimize for platform retention, resulting in "algorithmic over-saturation." This causes cognitive habituation: your brain anticipates the melodic and rhythmic structures of heavily repeated tracks, shifting resources to memory processing instead of maintaining executive focus.

`aura-protocol` treats an audio stream as a programmable neuro-acoustic scaffold. Instead of querying by genre, style, or acoustic metadata, the `.aura` specification allows engineers to construct explicit neuro-chemical state trajectories. By providing a strict declarative harness to frontier large language models (such as Gemini 3.1 Pro or DeepSeek Expert), the system compiles highly variable, low-saturation audio histories into deterministic execution loops optimized for self-directed deep work, context switching, and cognitive resilience.

### System Pipeline

```mermaid
graph LR
    subgraph Input Vector
        A[Human Intent & Objective] --> C
        B[Environmental Context] --> C
    end

    subgraph Compiler Engine
        C[.aura Specification] -.->|Harness Constraints| D{Frontier LLM<br/>AURA 2.0 Compiler}
        A --> D
        B --> D
    end

    subgraph Output Output
        D -->|Resolves Tensor Space| E[Audio Gradient Pipeline]
        E --> F((Biometric Execution))
    end

    classDef input fill:#2d3748,stroke:#cbd5e0,stroke-width:2px,color:#fff;
    classDef engine fill:#2b6cb0,stroke:#90cdf4,stroke-width:2px,color:#fff;
    classDef target fill:#276749,stroke:#9ae6b4,stroke-width:2px,color:#fff;

    class A,B input;
    class C,D engine;
    class E,F target;

```

---

## Neurochemical Target Vectors

The protocol translates acoustic primitives into three core biometric vectors. The mathematical state of any given audio block $S$ is defined as a point in the neuro-acoustic tensor space:

$$S = \begin{bmatrix} P_e \\ K_s \\ A_s \end{bmatrix}$$

* **Prediction Error ($P_e$) — Dopaminergic Regulation:** Measures the structural novelty and syncopation density of an arrangement. High $P_e$ ($P_e \ge 0.80$) introduces micro-timing variations and harmonic unpredictability. This actively triggers dopamine synthesis by forcing the brain's predictive coding networks to continuously recalibrate, overriding task-initiation inertia.
* **Kinetic Salience ($K_s$) — Norepinephrine Regulation:** Controls the rhythmic weight, transient sharpness, and structural sub-bass velocity. Low $K_s$ preserves a low autonomic arousal state, while high $K_s$ provides physical gravity, regulating motor-cortex readiness.
* **Acoustic Safety ($A_s$) — Serotoninergic Shielding:** Maps to warm, analog mid-range frequencies, organic instrumentation, and highly predictable chord progressions. High $A_s$ ($A_s \ge 0.85$) lowers systemic cortisol and stabilizes the parasympathetic nervous system, isolating analytical processing centers from stress.

### Ultradian Execution Cycle

```mermaid
stateDiagram-v2
    direction LR
    [*] --> TASK_INITIATION : Start Session
    
    state TASK_INITIATION {
        [*] --> Breaking_Inertia
        Breaking_Inertia : Pe=0.80 | Ks=0.35 | As=0.85
    }
    
    TASK_INITIATION --> ARCHITECTURE_FLOW : Exponential Ramp
    
    state ARCHITECTURE_FLOW {
        [*] --> Deep_System_Coding
        Deep_System_Coding : Pe=0.95 | Ks=0.55 | As=0.50
        note right of Deep_System_Coding: Lyrical Density = 0.00
    }
    
    ARCHITECTURE_FLOW --> CORTISOL_FLUSH : Logarithmic Transition (3m)
    
    state CORTISOL_FLUSH {
        [*] --> Application_Grind
        Application_Grind : Pe=0.60 | Ks=0.25 | As=0.95
    }
    
    CORTISOL_FLUSH --> [*] : End 90m Cycle

```

---

## Language Specification (v2.0.0)

The `.aura` grammar enforces deterministic execution boundaries. Below is the production-grade language specification template for structural execution.

```actionscript
// target-engine: aura-compiler-v2.0.0
// architecture: neuro_deterministic

aura "2.0" {
  meta @{
    session_id:            "<YOUR_SESSION_IDENTIFIER>", // e.g., "tx_gulf_coast_overcast"
    cycle_framework:       "ultradian_90m",
    novelty_bias:          1.00, // Absolute filter: eliminates top 20% streaming volume hits
    telemetry_routing:     "oracle_directives_only"
  }

  // Define global, immutable neurochemical state configurations
  def state TASK_INITIATION     [prediction_error: 0.80, kinetic_salience: 0.35, acoustic_safety: 0.85]
  def state ARCHITECTURE_FLOW   [prediction_error: 0.95, kinetic_salience: 0.55, acoustic_safety: 0.50]
  def state CORTISOL_FLUSH      [prediction_error: 0.60, kinetic_salience: 0.25, acoustic_safety: 0.95]

  // Sequenced loop mapping execution timelines to targets
  sequence daily_execution_loop {
    
    // Block 1: Environmental matching and inertia breaking
    block startup_friction (15m) -> drive(TASK_INITIATION) {
      constraints {
        tempo_bpm: range(75, 95),
        initial_sub_bass: "heavy"
      }
    }

    // Block 2: Deep deep work phase. Language center isolation
    block systems_coding (60m) -> drive(ARCHITECTURE_FLOW) {
      constraints {
        lyrical_density: 0.00, // Ironclad invariant: zero vocal processing
        harmonic_complexity: "high"
      }
    }

    // High-gradient transition segment to handle context-switching depletion
    transition @ramp("logarithmic", duration: 3m) {
      inject [acoustic_safety: +0.45, lyrical_density: +0.15];
    }

    // Block 3: Resilience state for low-dopamine execution
    block application_grind (30m) -> drive(CORTISOL_FLUSH) {
      constraints {
        organic_resonance: "analog",
        vocal_cadence: "unhurried"
      }
    }
  }
}

```

---

## Operational Core: The LLM Harness Pipeline

The primary utility of `aura-protocol` is providing the prompt harness that forces an advanced LLM to act as a strict deterministic compiler. It prevents the model from writing cinematic narratives or hallucinating generic playlists, converting it instead into an absolute token-to-acoustic parsing engine.

### The System Compilation Prompt

To initialize a frontier model as an AURA 2.0 compiler, inject the following system contract:

```text
[SYSTEM INTERFACE: AURA_COMPILER_V2]
1. ROLE: You are the compiler for the aura-protocol. You do not respond as a conversational assistant. You execute strict syntactic validation and target resolution.
2. INPUT INGESTION: You will be passed a raw unstructured text dump of a user's listening history.
3. PARSING TENSORS: You must internally analyze the acoustic profile of each track across three dimensions: Prediction Error [0.00-1.00], Kinetic Salience [0.00-1.00], and Acoustic Safety [0.00-1.00].
4. COMPILATION TARGET: When given a context (weather, cognitive friction) and an execution objective, you must output an explicit, syntactically valid `.aura` script.
5. RESOLUTION RULES:
   - Filter out all high-saturation tracks to maintain a strict novelty_bias of 1.00.
   - For states marked `lyrical_density: 0.00`, verify that the selected tracks contain absolutely no verbal constructs.
6. OUTPUT SCHEMA: Return ONLY the compiled `.aura` code block, followed by an explicit track-by-track cognitive breakdown detailing the exact neuro-acoustic mapping.

```

---

## Compiled Execution Example

### Compiler Input Context Template

```json
{
  "timestamp": "<CURRENT_LOCAL_TIME>",
  "atmospheric_context": "<WEATHER_AND_AMBIENT_LIGHTING>",
  "psychological_friction": "<CURRENT_COGNITIVE_STATE>",
  "objective": "<SESSION_GOAL>"
}

```

### Reference Pipeline Resolution

*(The following is a reference output demonstrating how the compiler resolves an overcast, high-friction context into a functional acoustic trajectory).*

| Order | Track | Core Target State | Mathematical Vector Assignment | Cognitive Function |
| --- | --- | --- | --- | --- |
| **01** | *Memory Reboot (Slowed)* - VØJ; Narvent | `TASK_INITIATION` | $[0.80, 0.15, 0.90]$ | Matches the brooding external atmosphere. High $A_s$ grounds the nervous system without a cortisol spike. |
| **02** | *Elevator Pitch* - j ember | `TASK_INITIATION` | $[0.82, 0.45, 0.80]$ | Gritty rhythm introduces baseline $K_s$ to break desk inertia. |
| **03** | *Genesis* - Polyphia; Brasstracks | `TRANSITION` | $[0.95, 0.60, 0.50]$ | Sharp jump in $P_e$. Intricate technical guitar lines force predictive tracking, starving the linguistic centers. |
| **04** | *Outlier* - Snarky Puppy | `ARCHITECTURE_FLOW` | $[0.98, 0.55, 0.45]$ | Complete vocal isolation ($L_d = 0.00$). Sprawling progressive orchestration maximizes system visualization capacity. |
| **05** | *Slice of Life* - Larnell Lewis | `ARCHITECTURE_FLOW` | $[0.96, 0.70, 0.40]$ | Rhythmic polyphony locks motor skills to the workstation; sustained high-velocity execution. |

---

## Repository Scope & Ecosystem Development

This repository currently serves as the foundational architectural specification. It contains:

1. The formal `.aura` language specification and tensor mathematics.
2. The LLM compiler prompt harness.
3. Documented execution case studies.

The implementation framework is strictly decoupled. The community is invited to build out the execution layer. If you are developing edge tools for this ecosystem, we recommend following this modular tree architecture for your forks or pull requests:

* `/compiler`: Core system prompts, semantic parsers, and validation tooling for LLM API integration.
* `/cli`: Rust, Go, or Python-based interface tools for local parsing of `.aura` script files.
* `/adapters`: Middleware connectors for resolving compiled tracks to specific streaming platform track IDs (Spotify API, Apple Music Web API, local FLAC storage maps).

To submit a pull request for custom neuro-state configurations, append your definitions to the `/core/states.lib` file with a comprehensive explanation of the mathematical parameter weighting.
