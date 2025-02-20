# HOMER Plotting Tools
![R](https://img.shields.io/badge/R-plots-blue.svg)
![HOMER](https://img.shields.io/badge/HOMER-compatible-green.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

A collection of R scripts for creating publication-quality visualizations from HOMER (Hypergeometric Optimization of Motif EnRichment) analysis outputs. This toolkit enhances HOMER's capabilities with customizable plotting functions for motif analysis, peak annotations, and genomic feature distributions.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Plot Types](#plot-types)
- [Configuration](#configuration)
- [Contributing](#contributing)

## Overview
This toolkit extends HOMER's functionality by providing advanced visualization capabilities for:
- Motif enrichment analysis
- Peak distribution plots
- Genomic feature annotations
- Tag density heatmaps
- Integration with other NGS data

## Features
- Publication-ready plot generation
- Customizable visualization parameters
- Multiple plot types and styles
- Batch processing capabilities
- Integration with HOMER outputs
- Statistical annotation options
- High-resolution export formats

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/rrjHomerPlots.git
cd rrjHomerPlots
```

2. Install R dependencies:
```R
install.packages(c(
  "ggplot2",
  "ComplexHeatmap",
  "GenomicRanges",
  "rtracklayer",
  "gridExtra"
))
```

3. Ensure HOMER is installed and in your PATH

## Usage

### Basic Plotting
```R
# Load the plotting library
source("homer_plots.R")

# Create motif enrichment plot
plot_motif_enrichment("path/to/homer/output", 
                     top_n = 10,
                     plot_type = "barplot")

# Generate peak distribution
plot_peak_distribution("path/to/peaks.txt",
                      genome = "hg19",
                      window_size = 2000)
```

### Batch Processing
```R
# Process multiple datasets
process_multiple_outputs(
  input_dir = "homer_results/",
  output_dir = "plots/",
  plot_types = c("motif", "distribution")
)
```

## Plot Types

### 1. Motif Enrichment
- Bar plots of enrichment scores
- Logo plots for motif sequences
- P-value distribution plots
- Combined motif-score visualizations

### 2. Peak Distribution
- Genome-wide distribution plots
- Feature-centered heatmaps
- Distance to TSS plots
- Chromosome-wise distribution

### 3. Feature Annotation
- Genomic feature pie charts
- Feature enrichment plots
- Region overlap plots
- Custom annotation plots

### 4. Tag Density
- Profile plots
- Heatmaps
- Aggregation plots
- Multi-sample comparisons

## Plot Customization

### Color Schemes
```R
# Default color palettes
homer_colors <- c(
  "primary" = "#4285F4",
  "secondary" = "#34A853",
  "accent" = "#EA4335"
)

# Custom theme settings
homer_theme <- theme_minimal() +
  theme(
    axis.text = element_text(size = 12),
    axis.title = element_text(size = 14, face = "bold")
  )
```

### Layout Options
```R
# Configure plot dimensions
plot_config <- list(
  width = 8,
  height = 6,
  dpi = 300,
  format = "pdf"
)
```

## Data Requirements

### Input Formats
1. HOMER output files
2. BED/narrowPeak files
3. Tag directories
4. Genome annotations

### File Structure
```
project/
├── data/
│   ├── peaks/          # Peak files
│   ├── motifs/         # Motif analysis
│   └── tags/           # Tag directories
└── output/
    └── plots/          # Generated plots
```

## Configuration

### Global Settings
```R
# Set global parameters
options(
  homer.genome = "hg19",
  homer.plot.width = 8,
  homer.plot.height = 6,
  homer.plot.dpi = 300
)
```

### Plot-Specific Settings
```R
# Motif plot settings
motif_params <- list(
  max_motifs = 10,
  p_cutoff = 0.05,
  sort_by = "p.value"
)

# Distribution plot settings
dist_params <- list(
  window = 2000,
  bin_size = 50,
  smooth = TRUE
)
```

## Contributing

1. Fork the repository
2. Create your feature branch
3. Add your plotting functions
4. Submit a pull request

### Development Guidelines
- Follow R style guidelines
- Document all functions
- Include example plots
- Add unit tests

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Citation
If you use these plotting tools in your research, please cite:
```
Author et al. (Year). HOMER Plotting Tools: Enhanced visualization for HOMER analysis.
Repository: https://github.com/yourusername/rrjHomerPlots
```

## Related Projects
- [HOMER](http://homer.ucsd.edu/homer/)
- [ATACseq_Pipeline](../ATACseq_Pipeline)
- [goronzy_lab](../goronzy_lab)

## Acknowledgments
- HOMER development team
- R visualization packages
- Supporting institutions
- Bioinformatics community
