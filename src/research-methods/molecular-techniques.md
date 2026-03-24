# Molecular Techniques in Wildlife Health Research

## Introduction

Molecular biology has transformed wildlife health research, enabling pathogen identification at unprecedented resolution, revealing transmission pathways invisible to traditional methods, and opening entirely new avenues of investigation such as environmental DNA and microbiome analysis. For wildlife veterinarians, familiarity with molecular techniques is essential for designing studies, interpreting results, and applying molecular data to clinical and conservation decisions. This chapter covers the major molecular methods used in wildlife health research today.

## Genomics and Whole Genome Sequencing

### Fundamentals

Whole genome sequencing (WGS) determines the complete DNA sequence of an organism's genome. Advances in sequencing technology have made WGS increasingly accessible and affordable for wildlife health applications.

### Sequencing Platforms

| Platform | Read Length | Throughput | Error Rate | Best For |
|----------|-----------|-----------|-----------|---------|
| Illumina (short-read) | 150-300 bp | Very high | Low (~0.1%) | Re-sequencing, variant calling, metagenomics |
| Oxford Nanopore (MinION) | Up to >100 kb | Moderate | Higher (~5%, improving) | Field sequencing, structural variants, long reads |
| PacBio (HiFi) | 10-25 kb (HiFi) | Moderate | Low (HiFi ~0.1%) | De novo assembly, structural variants |
| Ion Torrent | 200-600 bp | Moderate | ~1% | Targeted panels, smaller genomes |

### Applications in Wildlife Health

#### Pathogen Genomics
- **Complete pathogen genome assembly**: Enables comprehensive characterization of virulence factors, resistance genes, and evolutionary history
- **Variant identification**: Single nucleotide polymorphisms (SNPs) provide high-resolution strain typing for outbreak investigation
- **Recombination and reassortment analysis**: Critical for segmented viruses (influenza) and recombinogenic bacteria
- **Antimicrobial resistance gene identification**: In silico prediction of resistance phenotypes from genome sequences

#### Host Genomics
- **Population genetics**: Assess genetic diversity, population structure, and inbreeding in wildlife populations
- **Immunogenomics**: Characterize MHC diversity and immune gene variation in relation to disease susceptibility
- **Genome-wide association studies (GWAS)**: Identify genetic variants associated with disease resistance or susceptibility
- **Conservation genomics**: Inform management of genetically important populations

### Field Sequencing with Nanopore

The Oxford Nanopore MinION has enabled real-time sequencing in field settings:

- Portable device (approximately the size of a stapler) powered by a laptop
- Successfully deployed for Ebola virus sequencing in Guinea, Zika virus in Brazil, and avian influenza surveillance
- Enables rapid pathogen identification without shipping samples to reference laboratories
- Library preparation protocols are becoming simpler, though some still require laboratory equipment
- Analysis can be performed in real time as data are generated

## Metagenomics for Pathogen Discovery

### Concept

Metagenomics sequences all genetic material in a sample without prior knowledge of what organisms are present, enabling unbiased pathogen discovery:

- **Shotgun metagenomics**: Sequence all DNA (or cDNA from RNA) in a sample; computationally identify pathogen sequences
- **Targeted metagenomics (amplicon sequencing)**: Amplify and sequence specific marker genes (e.g., 16S rRNA for bacteria, ITS for fungi, COI for invertebrates) to characterize community composition

### Applications in Wildlife Health

- **Novel pathogen discovery**: Identify previously unknown viruses, bacteria, or parasites in wildlife die-offs
- **Characterizing pathogen communities**: Assess the full suite of pathogens carried by a wildlife species
- **Syndromic surveillance**: Screen for all potential pathogens in clinical samples when the causative agent is unknown
- **Virome characterization**: Comprehensive profiling of viral communities in wildlife, including novel viruses with pandemic potential

### Analytical Pipeline

1. **Sample processing**: Extract nucleic acids; deplete host DNA/RNA to enrich pathogen sequences (optional but improves sensitivity)
2. **Library preparation**: Prepare sequencing libraries appropriate for the platform
3. **Sequencing**: Generate reads
4. **Quality control**: Remove low-quality reads, adapter sequences, and host contamination
5. **Assembly**: De novo assembly of reads into contigs (e.g., SPAdes, MEGAHIT) or reference-based mapping
6. **Taxonomic classification**: Assign reads or contigs to taxa using databases (NCBI nr, Kraken2, DIAMOND)
7. **Functional annotation**: Identify genes of interest (virulence, resistance, metabolism)
8. **Novelty assessment**: BLAST analysis against known sequences; phylogenetic placement of novel organisms

### Challenges

- **Sensitivity**: Pathogen sequences may represent a tiny fraction of total reads; deep sequencing and host depletion are often necessary
- **Contamination**: Environmental and reagent contamination can produce false positives; negative controls are essential
- **Database limitations**: Novel organisms in wildlife may have no close relatives in reference databases
- **Computational demands**: Large datasets require substantial computing resources and bioinformatic expertise

## Environmental DNA (eDNA)

### Concept

Environmental DNA (eDNA) is genetic material shed by organisms into their environment through feces, mucus, skin cells, gametes, and decomposition. Collecting and analyzing eDNA from water, soil, or air samples enables species detection without directly observing or capturing animals.

### Methods

- **Sample collection**: Water filtered through fine membranes (typically 0.45 or 0.22 micrometer pore size); soil cores; air filters
- **DNA extraction**: Using commercial kits optimized for environmental samples
- **Detection approaches**:
  - **Species-specific qPCR/ddPCR**: Targeted detection of a single species using species-specific primers and probes
  - **Metabarcoding**: Amplification of universal barcode regions (e.g., 12S for vertebrates, COI for invertebrates) followed by high-throughput sequencing to detect multiple species simultaneously

### Applications in Wildlife Health

- **Disease surveillance**: Detect pathogen DNA in environmental samples (e.g., *Batrachochytrium dendrobatidis* in pond water, *Mycobacterium bovis* in soil at badger setts)
- **Host species monitoring**: Confirm presence of reservoir or vector species without trapping
- **Invasive species detection**: Early detection of invasive species that may carry novel pathogens
- **Biodiversity assessment**: Rapid community-level surveys to assess host community composition and its relationship to disease risk
- **Parasite detection**: Identify parasite life stages in environmental samples

### Considerations

- eDNA degrades rapidly in the environment (days to weeks depending on conditions); detection indicates recent presence but not current occupancy
- False positives from contamination or DNA transport (e.g., carried by water flow from upstream) must be managed through appropriate controls
- Quantitative interpretation is limited; eDNA concentration does not reliably indicate population size
- Standardization of methods is ongoing; adherence to emerging best practices is important

## Phylogenetics and Phylogeography

### Phylogenetics

Phylogenetic analysis reconstructs evolutionary relationships among organisms using genetic sequence data:

- **Alignment**: Multiple sequence alignment of homologous sequences (MAFFT, MUSCLE, CLUSTAL)
- **Tree-building methods**:
  - **Maximum likelihood (ML)**: Finds the tree that maximizes the probability of observing the data given a model of sequence evolution (RAxML, IQ-TREE)
  - **Bayesian inference**: Estimates the posterior probability distribution of trees using Markov chain Monte Carlo (BEAST, MrBayes)
  - **Neighbor-joining**: Distance-based method; fast but less rigorous; useful for exploratory analysis (MEGA)
- **Support assessment**: Bootstrap values (ML) or posterior probabilities (Bayesian) quantify confidence in tree topology

### Applications in Wildlife Disease

- **Source attribution**: Determine whether a wildlife pathogen outbreak originated from domestic animals, other wildlife, or humans
- **Transmission directionality**: Phylogenetic evidence can indicate whether pathogen flow is from wildlife to livestock or vice versa
- **Cross-species transmission events**: Identify spillover and spillback events by placing wildlife and domestic animal isolates within a phylogenetic framework
- **Molecular clock analysis**: Estimate when divergence events occurred; reconstruct the timing and geographic spread of epidemics (BEAST software)

### Phylogeography

Phylogeography combines phylogenetics with geographic data to understand the spatial dynamics of genetic diversity:

- Map genetic lineages onto geography to reveal dispersal routes, barriers, and refugia
- Reconstruct the geographic spread of pathogens during outbreaks
- Identify source populations for disease introduction events
- Tools: BEAST with discrete or continuous phylogeographic models; SpreaD3 for visualization

## Molecular Epidemiology

### Multi-Locus Sequence Typing (MLST)

MLST characterizes bacterial isolates by sequencing internal fragments of multiple (typically seven) housekeeping genes:

- Each unique combination of alleles defines a sequence type (ST)
- STs are grouped into clonal complexes (CCs) representing lineages
- Standardized databases (PubMLST.org) enable comparison across studies and geographic regions
- Applications: Tracking *Salmonella*, *Campylobacter*, *Leptospira*, and other bacterial pathogens across wildlife, domestic animal, and human populations

### WGS-Based Typing

Whole genome sequencing provides the highest resolution for molecular epidemiology:

- **Core genome MLST (cgMLST)**: Extends MLST to hundreds or thousands of core genes; standardized schemes available for many pathogens
- **SNP analysis**: Identifies all single nucleotide differences between isolates; enables precise transmission chain reconstruction
- **Phylogenomic analysis**: Whole genome phylogenies provide both evolutionary context and epidemiological resolution
- **Cluster detection**: Genomic clusters (isolates differing by fewer than a defined SNP threshold) indicate epidemiological links

### Wildlife Applications

- Determining whether *E. coli* or *Salmonella* isolates from wildlife are related to human clinical or livestock isolates
- Tracing the geographic spread of wildlife pathogens (e.g., chronic wasting disease prion strains, avian influenza subtypes)
- Distinguishing local transmission from repeated independent introduction events
- Identifying antimicrobial resistance gene dissemination pathways between wildlife, environment, and domestic populations

## CRISPR-Based Diagnostics

### Emerging Diagnostic Platforms

CRISPR (Clustered Regularly Interspaced Short Palindromic Repeats) technology has been adapted for rapid, sensitive, and specific nucleic acid detection:

- **SHERLOCK** (Specific High-sensitivity Enzymatic Reporter UnLOCKing): Uses Cas13 to detect RNA targets; combined with isothermal amplification (RPA) for sensitivity; lateral flow readout enables field deployment
- **DETECTR** (DNA Endonuclease-Targeted CRISPR Trans Reporter): Uses Cas12 for DNA detection with similar principles

### Advantages for Wildlife Applications

- **Rapid**: Results in under an hour
- **Portable**: Minimal equipment required; suitable for field or remote laboratory settings
- **Specific**: Guide RNA can be designed for any pathogen target
- **Sensitive**: Attomolar detection limits when combined with amplification
- **Multiplexable**: Multiple targets can be detected simultaneously

### Current Status

- Validated for human pathogens (SARS-CoV-2, Zika, Ebola); wildlife applications emerging
- Potential for rapid field diagnosis of wildlife diseases (avian influenza, chytrid fungus, African swine fever)
- Challenges include primer/guide RNA design for genetically diverse wildlife pathogens, validation in non-model species, and regulatory approval for field use

## Microbiome Analysis in Wildlife

### The Wildlife Microbiome

Every wildlife species hosts complex microbial communities that influence health, nutrition, immunity, and behavior:

- **Gut microbiome**: Affects nutrient absorption, immune development, pathogen resistance, and potentially behavior
- **Skin/mucosal microbiome**: First-line defense against pathogens; involved in amphibian resistance to chytrid fungus
- **Respiratory microbiome**: Influences susceptibility to respiratory pathogens

### Methods

1. **Sample collection**: Fecal samples (non-invasive), swabs (cloacal, oral, skin), gut contents (necropsy)
2. **DNA extraction**: Using kits appropriate for the sample type; must be standardized across samples
3. **16S rRNA gene amplicon sequencing**: Standard approach for bacterial community profiling
   - Amplify variable regions (V3-V4 or V4 most common)
   - Sequence on Illumina platforms
   - Analyze using QIIME2, DADA2, or mothur pipelines
4. **ITS sequencing**: For fungal community profiling
5. **Shotgun metagenomics**: For functional characterization and higher taxonomic resolution

### Analytical Considerations

- **Alpha diversity**: Within-sample diversity (Shannon index, observed ASVs, Faith's phylogenetic diversity)
- **Beta diversity**: Between-sample diversity (Bray-Curtis, UniFrac, Jaccard distances; visualized with PCoA or NMDS)
- **Differential abundance**: Identify taxa that differ between health states, habitats, or species (DESeq2, ANCOM-BC, ALDEx2)
- **Functional prediction**: Infer metabolic potential from taxonomic composition (PICRUSt2) or from shotgun metagenomic data (HUMAnN)

### Applications in Wildlife Health

- **Health biomarkers**: Identifying microbiome signatures associated with disease, captivity, or environmental stress
- **Probiotic development**: Characterizing protective microbial communities (e.g., anti-*Bd* bacteria on amphibian skin) as potential conservation tools
- **Captive management**: Assessing microbiome changes in captive versus wild populations and their implications for reintroduction success
- **Diet and nutrition**: Linking microbiome composition to dietary quality and nutritional status
- **Disease susceptibility**: Understanding how microbiome disruption (dysbiosis) predisposes to infectious disease

### Challenges Specific to Wildlife

- Limited reference databases for wildlife-associated microbes
- High inter-individual variation, especially in free-ranging populations
- Difficulty controlling for confounding variables (diet, season, habitat, capture stress)
- Sample preservation in field conditions (cold chain, preservatives)
- Small sample sizes for rare species

## Integrating Molecular Data

### Multi-Omic Approaches

Combining multiple molecular data types provides richer understanding:

- **Genomics + transcriptomics**: How does host gene expression change in response to infection?
- **Metagenomics + metabolomics**: What metabolic interactions occur between host and microbiome?
- **Pathogen genomics + host immunogenomics**: How do pathogen and host genetic variation interact to determine disease outcomes?

### Bioinformatic Infrastructure

- High-performance computing or cloud computing (AWS, Google Cloud) for computationally intensive analyses
- Standardized bioinformatic pipelines for reproducibility
- Version control for analysis code (Git/GitHub)
- Public data repositories (NCBI SRA, ENA, MG-RAST) for data sharing and archiving

## Summary

Molecular techniques have become indispensable tools in the wildlife veterinarian's research toolkit. From whole genome sequencing of pathogens to environmental DNA surveys, from CRISPR-based field diagnostics to microbiome profiling, these methods provide resolution and insight that would be impossible with traditional approaches alone. Wildlife veterinarians need not become molecular biologists, but they must understand the capabilities, limitations, and practical requirements of these techniques to design meaningful studies, collaborate effectively with laboratory scientists, and interpret molecular data in the context of wildlife health and conservation.
