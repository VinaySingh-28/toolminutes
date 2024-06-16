# Tandem mass spectrum prediction for small molecules using graph transformers

**Authors:** Young, A., Röst, H.

**DOI:** [doi:10.1038/s42256-024-00816-8](https://doi.org/10.1038/s42256-024-00816-8)

**Published:** April 2024

**Journal:** Nat Mach Intell

## Why discuss this paper?
- The article primarily focuses on metabolite analysis and small-molecule structure elucidation using deep learning approaches.
### Overview of MIST

```mermaid
%%{init: {"flowchart": {"htmlLabels": true}} }%%
flowchart LR;

Introduction_MIST["<b><center>Introduction to MIST</center></b>"] --> Neural_Network_Approach["Neural Network Approach"];
Introduction_MIST --> Spectrum_Representation["Spectrum Representation"];
Introduction_MIST --> Inductive_Biases_and_Features["Inductive Biases and Features"];
Inductive_Biases_and_Features --> Neutral_Loss_Relationships{{"Neutral Loss Relationships"}};
Inductive_Biases_and_Features --> Simultaneous_Predictions{{"Simultaneous Predictions"}};
Inductive_Biases_and_Features --> In_Silico_Forward_Augmentation{{"In Silico Forward Augmentation"}};
Inductive_Biases_and_Features --> Novel_Unfolding_Architecture{{"Novel 'Unfolding' Architecture"}};
Spectrum_Representation --> Chemical_Formulae_of_Peaks{{"Uses chemical formulae of peaks"}};
Spectrum_Representation --> Inspired_by_CSI_FingerID{{"Inspired by CSI:FingerID"}};

Introduction_MIST --> Enhancing_Spectra_Annotation["<b><center>Enhancing Spectra Annotation</center></b>"];
Enhancing_Spectra_Annotation --> Contrastive_Representation_Learning{{"Contrastive Representation Learning"}};

Introduction_MIST --> Model_Evaluation["<b><center>Model Evaluation</center></b>"];
Model_Evaluation --> Ablation_Studies{{"Ablation Studies"}};

Introduction_MIST --> Real_World_Application["<b><center>Real-World Application</center></b>"];
Real_World_Application --> Clinical_Sample_Analysis{{"Clinical Sample Analysis"}};
Real_World_Application --> Propose_New_Annotations{{"Propose New Annotations"}}

```
![Figure 1](./Fig1.png)
<br>

```mermaid
%%{init: {"flowchart": {"htmlLabels": true}} }%%
flowchart LR;

Mass_Spectrometry_MS["<b>Mass Spectrometry (MS)</b>"]
Mass_Spectrometry_MS --> Identifies_quantifies_chemicals["Identifies and quantifies chemicals in a mixture"]
Mass_Spectrometry_MS --> Ionized_detected_mass_analyzer["Molecules are ionized and detected by mass analyzer"]
Mass_Spectrometry_MS --> Records_mass_charge_ratio["Records mass-to-charge ratio (m/z)"]

Tandem_MS_MS["<b>Tandem Mass Spectrometry (MS/MS)</b>"]
Tandem_MS_MS --> Includes_fragmentation_step["Includes fragmentation step"]
Tandem_MS_MS --> Breaks_down_molecules["Breaks down molecules into smaller fragments"]
Tandem_MS_MS --> Infers_molecular_structure["Infers molecular structure of original molecule"]

LC_MS_MS["<b>LC-MS/MS</b>"]
LC_MS_MS --> Combines_liquid_chromatography["Combines liquid chromatography for separation"]
LC_MS_MS --> Used_in_various_fields["Used in proteomics, metabolomics, forensics, environmental chemistry"]

Mass_Spectrometry_MS --> Tandem_MS_MS
Mass_Spectrometry_MS --> LC_MS_MS
```

```mermaid
%%{init: {"flowchart": {"htmlLabels": true}} }%%
flowchart LR;

Challenges_in_MS["<b>Challenges in MS</b>"]
Challenges_in_MS --> Accurate_simulation_difficult["Accurate simulation of fragmentation is difficult"]
Challenges_in_MS --> Simulations_slow_approximate["First principles simulations are slow and approximate"]
Challenges_in_MS --> Incomplete_spectral_databases["Incomplete spectral databases hinder compound identification"]
```

```mermaid
%%{init: {"flowchart": {"htmlLabels": true}} }%%
flowchart LR;

Existing_Solutions_Limitations["<b>Existing Solutions and Limitations</b>"]

Database_Searches["Database Searches"]
Database_Searches --> Rely_large_libraries["Rely on large reference libraries and spectrum similarity functions"]
Database_Searches --> Poor_coverage["Databases have poor coverage"]

In_Silico_Spectra["In Silico Spectra"]
In_Silico_Spectra --> Augments_libraries["Augments spectral libraries with simulated spectra"]
In_Silico_Spectra --> Improves_coverage_match["Improves coverage and match finding"]

Competitive_Fragmentation_Modelling["Competitive Fragmentation Modelling (CFM)"]
Competitive_Fragmentation_Modelling["Competitive Fragmentation Modelling (CFM)"] --> Combinatorial_fragmentation["Combines combinatorial fragmentation and probabilistic modeling"]
Competitive_Fragmentation_Modelling["Competitive Fragmentation Modelling (CFM)"] --> Slow_struggles_larger_compounds["Slow and struggles with larger compounds"]

Deep_Learning_Approaches["Deep Learning Approaches"]
Deep_Learning_Approaches --> Fully_connected_networks["Use fully connected neural networks or graph neural networks"]
Deep_Learning_Approaches --> Focus_local_structures["Focus on local structures"]
Deep_Learning_Approaches --> Struggle_global_interactions["Struggle with modeling global interactions"]

Existing_Solutions_Limitations --> Database_Searches
Existing_Solutions_Limitations --> In_Silico_Spectra
Existing_Solutions_Limitations --> Competitive_Fragmentation_Modelling
Existing_Solutions_Limitations --> Deep_Learning_Approaches
```

```mermaid
%%{init: {"flowchart": {"htmlLabels": true}} }%%
flowchart LR;

Development_of_MassFormer["<b>Development of MassFormer</b>"]
Development_of_MassFormer --> Adapts_graph_transformer["Adapts graph transformer architecture for MS/MS spectrum prediction"]
Development_of_MassFormer --> Graph_transformers_model["Graph Transformers model pairwise interactions between all nodes"]
Development_of_MassFormer --> Captures_local_global["Captures both local and global structural information"]
Development_of_MassFormer --> Unique_Positional_Encoding["Unique Positional Encoding uses degree and shortest path information"]
```

```mermaid
%%{init: {"flowchart": {"htmlLabels": true}} }%%
flowchart LR;

Advantages_of_MassFormer["<b>Advantages of MassFormer</b>"]

Accurate_Predictions["Accurate Predictions"]
Accurate_Predictions --> State_of_the_art["State-of-the-art performance in spectrum prediction"]
Accurate_Predictions --> Outperforms_existing_methods["Outperforms existing baseline methods"]

Global_Interactions["Global Interactions"]
Global_Interactions --> Models_global_interactions["Models global interactions between distant atoms"]
Global_Interactions --> Improves_understanding["Improves understanding of fragmentation events"]

Efficiency["Efficiency"]
Efficiency --> Leverages_pretrained_models["Leverages pretrained graph transformer models"]
Efficiency --> Accurate_predictions["Provides accurate predictions without excessive computational costs"]

Real_World_Applications["Real-World Applications"]
Real_World_Applications --> Validated_spectrum_identification["Validated for spectrum identification problems"]
Real_World_Applications --> Handles_collision_energy["Handles effects of collision energy on spectra"]

Advantages_of_MassFormer --> Accurate_Predictions
Advantages_of_MassFormer --> Global_Interactions
Advantages_of_MassFormer --> Efficiency
Advantages_of_MassFormer --> Real_World_Applications
```

### Summary:

- **Metabolite Analysis:**
  - Relative abundances of piperidine and pyridine alkaloids in healthy, UC, and CD patient groups are compared.
  - Total number of metabolites and novel structures identified are discussed.
  - Abundance fold changes between healthy, UC, and CD cohorts are analyzed.
  - Annotated molecule structures for select compounds are presented.

- **MIST Model:**
  - MIST accurately predicts compound fingerprints from mass spectra.
  - Contrastive fine-tuning improves metabolite retrieval.
  - The model demonstrates strong accuracy on various metabolite classes.

- **Future Directions:**
  - Need for standardized benchmarks in mass spectrometry model development.
  - Exploration of retrieval task complexities and potential biases in predictions.
### Code availability
All code to replicate experiments, train new models and load pretrained models is available at https://github.com/samgoldman97/mist.

## Takeaways
- Metabolite analysis compares healthy, UC, and CD patient groups, focusing on piperidine and pyridine alkaloids.
- The MIST model accurately predicts compound fingerprints from mass spectra with high accuracy.
- Future directions involve standardizing benchmarks in mass spectrometry model development and exploring retrieval task complexities and biases in predictions.



[def]: papers/Metabolite_MS_Transformer/Figures/Fig1.png