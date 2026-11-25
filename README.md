# PyMol

A lightweight, single-file web application for interactive protein sequence analysis, domain mapping, and 3D molecular visualization. Built with vanilla HTML, CSS, SVG, and JavaScript, it fetches live biological data directly from UniProt and RCSB PDB/PDBe with zero build steps or backend dependencies.

By default, it loads human **CREB1** (UniProt: `P16220`, PDB: `1DH3`), but you can query any UniProt accession and PDB ID.

## Preview

### Domain Map & Color-Coded Sequence
![Domain Map and Sequence Viewer](./assets/overview.png)

### Composition, Hydrophobicity & Interactive 3D Structure
![Amino Acid Composition, Hydrophobicity Plot, and 3D Structure Viewer](./assets/analytics-3d.png)

## Features

* **Live UniProtKB Integration**: Fetches protein names, organism details, full amino acid sequences, and feature annotations directly from the UniProt REST API. Includes a manual fallback prompt to paste plain or FASTA sequences if offline.
* **Interactive Domain & Feature Map**: Custom SVG track displaying Domains, DNA-binding regions, Regions, Motifs, and Compositional bias in non-overlapping lanes. Phosphorylation sites are highlighted as red lollipop markers. Hover over any element for residue coordinates and descriptions.
* **Color-Coded Sequence Viewer**: Renders the amino acid sequence in 10-residue blocks (60 per line) with residue indices and hover tooltips. Residues are grouped by physicochemical properties:
  * **Hydrophobic**: `A, V, I, L, M, F, W, Y`
  * **Polar**: `S, T, N, Q`
  * **Basic (+)**: `K, R, H`
  * **Acidic (-)**: `D, E`
  * **Special**: `G, P, C`
* **Amino Acid Composition Chart**: Interactive SVG bar chart showing exact counts and percentages for all 20 standard amino acids, color-coded by property.
* **Hydrophobicity Profile**: Sliding-window Kyte-Doolittle hydropathy plot (window size = 9) highlighting hydrophobic (`> 0`) and hydrophilic (`< 0`) regions across the sequence.
* **Interactive 3D Structure Viewer**: Powered by `3Dmol.js` with automatic multi-CDN fallback and multi-mirror PDB fetching (RCSB PDB and PDBe).
  * Toggle between **Cartoon**, **Sticks**, and **Surface** representations.
  * Automatically distinguishes protein chains (colored by chain) from nucleic acids (rendered as sticks).
  * Supports drag-to-rotate and scroll-to-zoom controls.
* **Adaptive UI**: Responsive layout with automatic Light and Dark mode support via `prefers-color-scheme`.

## Getting Started

No installation, Node.js, or bundler is required.

1. Clone or download this repository:
   ```bash
   git clone [https://github.com/ianchitdas/PyMol.git](https://github.com/ianchitdas/PyMol.git)
   cd PyMol
