# Genetic Considerations in Conservation Medicine

## Overview

Genetics underpins many aspects of wildlife health that are relevant to conservation medicine. Genetic diversity influences disease susceptibility, adaptive potential, reproductive fitness, and long-term population viability. Wildlife veterinarians must understand genetic principles to interpret health findings, design translocation programs, manage captive populations, and contribute to conservation planning.

## Genetic Diversity Assessment

### Why Genetic Diversity Matters for Health

Genetic diversity provides the raw material for adaptation to changing environments, including evolving pathogens. Populations with reduced genetic diversity face several health-related consequences:

- Reduced ability to mount diverse immune responses to novel pathogens
- Accumulation of deleterious alleles that cause genetic disease
- Decreased fertility and offspring viability (inbreeding depression)
- Reduced adaptive capacity to environmental stressors including climate change

### Measuring Genetic Diversity

**Heterozygosity**: The proportion of loci at which an individual (or on average across a population) carries two different alleles. Higher heterozygosity generally indicates greater genetic diversity.

- **Observed heterozygosity (Ho)**: Directly measured from genotype data
- **Expected heterozygosity (He)**: Predicted from allele frequencies under Hardy-Weinberg equilibrium
- **Comparison of Ho and He**: Ho < He suggests inbreeding or population subdivision

**Allelic richness**: The number of distinct alleles per locus, corrected for sample size. Allelic richness is more sensitive to population bottlenecks than heterozygosity because rare alleles are lost first.

**Nucleotide diversity (pi)**: The average number of nucleotide differences per site between pairs of DNA sequences. Useful for sequence-based analyses.

**Effective population size (Ne)**: The size of an idealized population that would experience the same rate of genetic drift as the actual population. Almost always much smaller than the census population size (N). Key thresholds:

| Ne Threshold | Significance |
|---|---|
| Ne < 50 | Immediate risk of inbreeding depression |
| Ne = 50-500 | Short-term genetic viability concerns |
| Ne > 500 | Generally considered adequate for maintaining adaptive potential |
| Ne > 1000 | Recommended for long-term evolutionary potential |

### Molecular Markers for Diversity Assessment

| Marker Type | Advantages | Limitations |
|---|---|---|
| Microsatellites (SSRs) | Well-established, highly polymorphic, codominant | Limited genomic coverage, ascertainment bias |
| SNP arrays | Genome-wide coverage, standardizable, high throughput | Require species-specific development or cross-species validation |
| Whole genome sequencing | Complete information, detects all variation types | Expensive, computationally demanding, requires reference genome |
| Mitochondrial DNA | Maternal lineage tracking, useful for phylogeography | Single locus, no information on nuclear diversity |
| MHC genes | Directly relevant to immune function | Complex gene family, technically challenging |

## Inbreeding Depression and Immune Function

### Mechanisms

Inbreeding depression occurs when mating between relatives increases homozygosity, exposing deleterious recessive alleles and reducing heterozygote advantage. The immune system is particularly sensitive to inbreeding because:

- **Major Histocompatibility Complex (MHC)**: MHC genes are the most polymorphic loci in vertebrate genomes. Heterozygosity at MHC loci allows recognition of a broader array of pathogen-derived peptides. Inbreeding reduces MHC heterozygosity and compromises pathogen recognition.
- **Innate immune genes**: Complement, toll-like receptors, and other innate immune components show functional variation that is reduced by inbreeding.
- **Overall genomic homozygosity**: Genome-wide inbreeding depression affects multiple physiological systems including immune cell development, cytokine production, and inflammatory responses.

### Evidence from Wildlife

Numerous studies have documented the link between inbreeding and disease susceptibility in wild populations:

- **Florida panther (*Puma concolor coryi*)**: Before genetic rescue, the highly inbred population showed elevated rates of cryptorchidism, cardiac defects, kinked tails, and susceptibility to infectious disease. Introduction of Texas pumas dramatically improved health metrics.
- **Swedish adders (*Vipera berus*)**: Isolated, inbred populations showed reduced offspring viability. Introduction of males from other populations reversed the decline.
- **Tasmanian devil**: Low MHC diversity may have contributed to the population's susceptibility to devil facial tumor disease, a transmissible cancer.
- **Cheetah (*Acinonyx jubatus*)**: Famously low genetic diversity correlates with high susceptibility to feline infectious peritonitis and other diseases.

### Measuring Inbreeding

- **Pedigree-based inbreeding coefficient (F)**: Calculated from known parentage. Accurate when pedigrees are complete but unavailable for most wild populations.
- **Molecular estimates of inbreeding**: Internal relatedness, homozygosity by loci, runs of homozygosity (ROH). ROH analysis from whole genome data is the current gold standard as it detects both recent and ancient inbreeding.

## Minimum Viable Population Genetics

### The MVP Concept

Minimum Viable Population (MVP) is the smallest population size with a high probability of persisting for a defined time period (commonly 99% probability of persistence for 100 years). Genetic considerations set a lower bound on MVP:

- Populations must be large enough to avoid critical loss of genetic diversity through drift
- The "50/500 rule" (Ne = 50 for short-term, Ne = 500 for long-term) has been influential but is increasingly viewed as a rough guideline
- Recent analyses suggest Ne > 100 for short-term and Ne > 1000 for long-term viability may be more appropriate
- The relationship between census size (N) and effective size (Ne) varies widely among species (Ne/N ratios range from 0.1 to 0.9)

### Genetic Erosion in Small Populations

Small populations lose genetic diversity through:

- **Genetic drift**: Random fluctuation in allele frequencies. Rate of diversity loss is approximately 1/(2Ne) per generation.
- **Fixation of deleterious alleles**: In small populations, selection is less effective at removing harmful mutations
- **Loss of rare alleles**: Rare alleles, which may include important adaptive variants, are disproportionately vulnerable to loss through drift

## Genetic Rescue

### Definition and Rationale

Genetic rescue involves introducing genetic material from outbred or genetically divergent populations to improve fitness in small, inbred populations. It counteracts inbreeding depression and restores adaptive genetic variation.

### Implementation Considerations

**When to consider genetic rescue**:
- Evidence of inbreeding depression (reduced survival, reproduction, or disease resistance)
- Effective population size below critical thresholds
- No natural gene flow to counteract genetic erosion
- Source populations with compatible but distinct genetic backgrounds are available

**Risks to evaluate**:
- **Outbreeding depression**: If source and recipient populations are too genetically divergent, hybrid offspring may have reduced fitness due to disrupted local adaptation or genetic incompatibilities
- **Disease introduction**: Translocated individuals may carry novel pathogens (see Translocation Health chapter)
- **Swamping of local adaptation**: Too many immigrants may dilute locally adaptive alleles
- **Taxonomic concerns**: Mixing genetically distinct populations may compromise the genetic identity of recognized subspecies or ESUs

**Decision framework for outbreeding depression risk** (based on Frankham et al. criteria):
1. Are the populations the same species? If no, high risk.
2. Have they been isolated for >500 years? If yes, moderate risk.
3. Are environments very different? If yes, moderate risk.
4. Are there fixed chromosomal differences? If yes, high risk.
5. If low risk on all counts, genetic rescue is likely to be beneficial.

### Success Stories

- **Florida panther**: Introduction of 8 female Texas pumas in 1995 reversed inbreeding depression. Survival, reproduction, and disease resistance improved significantly. Population grew from approximately 20-25 to over 200 individuals.
- **Mountain pygmy-possum (*Burramys parvus*)**: Translocation of males between isolated populations improved genetic diversity and offspring survival.
- **Bighorn sheep**: Multiple populations have benefited from translocations that restored genetic diversity and improved lamb survival.

## Genomic Tools

### SNP Arrays

Single nucleotide polymorphism (SNP) arrays provide standardized, high-throughput genotyping across thousands to hundreds of thousands of loci:

- Species-specific arrays available for several conservation-priority species (e.g., Tasmanian devil, koala, great apes)
- Cross-species application from closely related domestic species is sometimes feasible
- Applications include parentage assignment, relatedness estimation, population structure, inbreeding assessment, and genome-wide association studies for health traits

### Whole Genome Sequencing (WGS)

WGS provides complete genetic information and is increasingly affordable:

- Identifies all variant types (SNPs, insertions/deletions, structural variants, copy number variants)
- Enables detection of runs of homozygosity for precise inbreeding assessment
- Allows identification of genes under selection, including immune genes
- Reference genomes are available or in development for many wildlife species through initiatives like the Vertebrate Genomes Project and Earth BioGenome Project
- Low-coverage WGS (1-5x) can be cost-effective for population-level studies

### Reduced Representation Sequencing

Methods that sequence a subset of the genome provide a cost-effective middle ground:

- **RADseq (Restriction site Associated DNA sequencing)**: Sequences DNA fragments adjacent to restriction enzyme cut sites. Thousands of SNPs without a reference genome.
- **GBS (Genotyping By Sequencing)**: Similar to RADseq with simplified library preparation.
- **Target capture**: Sequencing of pre-selected genomic regions (e.g., immune genes, adaptive loci).

## Ancient DNA

### Applications in Conservation Medicine

Ancient DNA (aDNA) from museum specimens, subfossils, and archaeological material provides a historical baseline for understanding genetic change:

- **Historical diversity levels**: Quantify how much genetic diversity has been lost over time
- **Historical range and connectivity**: Determine pre-decline population structure and gene flow patterns
- **Pathogen detection**: Identify historical pathogen presence and evolution from archival specimens
- **Adaptive variation**: Determine which adaptive alleles existed historically and have been lost

### Technical Considerations

- DNA degrades over time; aDNA is typically fragmented and chemically modified
- Contamination prevention is critical; dedicated clean room facilities are standard
- Next-generation sequencing has revolutionized aDNA by enabling efficient sequencing of short fragments
- Museum specimens (skins, skeletons, fluid-preserved material) vary widely in DNA preservation quality

## Landscape Genetics

### Connecting Genetics and Geography

Landscape genetics integrates population genetics with landscape ecology to understand how landscape features influence gene flow and genetic structure:

- **Isolation by distance**: Gene flow decreases with geographic distance
- **Isolation by resistance**: Landscape features (roads, rivers, mountains, land cover types) create variable resistance to movement and gene flow
- **Corridor identification**: Landscape genetic analyses can identify functional corridors where gene flow actually occurs
- **Barrier detection**: Identify landscape features that restrict gene flow and isolate populations

### Health Relevance

Landscape genetic patterns directly affect disease dynamics and population health:

- Corridors that facilitate gene flow also facilitate pathogen spread
- Genetically isolated populations may lack exposure to and resistance against pathogens circulating in connected populations
- Management of connectivity must balance genetic health benefits against disease transmission risks

## Genetic Management of Captive Populations

### Goals

Captive population genetic management aims to:

- Retain 90% of source population genetic diversity for 100 years (or a specified number of generations)
- Minimize inbreeding accumulation
- Maintain demographic stability
- Avoid genetic adaptation to captivity

### Tools and Strategies

**Pedigree management**:
- Studbook software (ZIMS/SPARKS, PMx) calculates kinship coefficients and recommends pairings
- Mean kinship (MK) strategy: Prioritize breeding of individuals that are least related to the rest of the population
- Equalize founder contributions where possible

**Molecular tools to supplement pedigrees**:
- Parentage verification and assignment when pedigrees are incomplete
- Relatedness estimation for wild-caught founders with unknown pedigrees
- Detection of pedigree errors

**Practical challenges**:
- Animals may not cooperate with recommended pairings
- Space limitations restrict population size
- Behavioral, veterinary, and logistical constraints complicate genetic recommendations
- Balancing genetic diversity retention with individual animal welfare

### Genetic Adaptation to Captivity

Captive populations may undergo genetic changes that reduce fitness upon reintroduction:

- Selection for tameness and tolerance of captive conditions
- Relaxed natural selection for foraging ability, predator avoidance, and disease resistance
- Genetic drift in small captive populations

**Mitigation strategies**:
- Maximize effective population size to minimize drift
- Minimize generations in captivity
- Equalize family sizes to reduce selection response
- Consider periodic introduction of wild-caught individuals
- Provide naturalistic environments that maintain relevant behavioral and physiological traits
