---
tags:
  - Programming Languages
  - Software Engineering
  - Tooling
---

# 20026-10-30 — Introduction to Rust programming language

## Resource watched

**Title:** [Rust Tutorial #1 - Introduction To Rust Programming](https://www.youtube.com/watch?v=T_KrYLW4jw8&list=PLzMcBGfZo4-nyLTlSRBvo0zjSnCnqjHYQ)

**Type:** Video (followed by discussion)

## Summary and takeaways

Rust benefits: 
- Compiled language (hence faster than Python) and and strongly typed (hence prevention of many runtime errors).
- Very uniform ecosystem that helps to format, test and run your code (don't depend on many random tools like with Python).
- Combines low level and high level features depending on what you need from the language.
- Develop CLI tools and libraries (with Python bindings!).

Rust is a well-established language with big and active community. More applications in bioinformatics and molecular simulation are emrging.

`main.rs` is the convention for the main entry for any stand-alone programs

```rust
fn main() {
    println!("Hello world")
}
```

Similarly to Python, it has functions, classes and many other familiar but also unique and helpful features.

## Resources to start using Rust

- If you are a reader-learner, look at the [Rust book](https://doc.rust-lang.org/book/) by Rust developers. It contains all the key concepts as well as deep-dive explanations with code exapmles.

- Plenty tutorials and playlists on YouTube like [the one we started watching today](https://www.youtube.com/watch?v=T_KrYLW4jw8&list=PLzMcBGfZo4-nyLTlSRBvo0zjSnCnqjHYQ).

## Molecular simulation and structural bioinformatic tools and libraries in Rust

### 1. Molecular dynamics and molecular simulation engines

- [Lumol](https://github.com/lumol-org/lumol). General-purpose molecular simulation engine supporting classical molecular dynamics and Monte Carlo simulations. **Project is archived**
- [Faunus](https://github.com/mlund/faunus-rs). Monte Carlo molecular simulation framework for soft matter, electrolytes, and coarse-grained systems.
- [hoomd-rs](https://github.com/glotzerlab/hoomd-rs). Particle simulation framework for Monte Carlo simulations of hard shapes and interacting particles.
- [Velvet](https://github.com/seatonullberg/velvet). Experimental classical atomistic simulation engine.
- [Molchanica](https://github.com/David-OConnor/molchanica). Molecular visualization, editing, and simulation application.
- [dualis](https://github.com/YounghyeonPark/dualis). Multiphysics simulation framework with molecular dynamics functionality.

### 2. Molecular dynamics trajectory analysis

- [MolAR (molar)](https://github.com/yesint/molar). Molecular modeling and trajectory analysis with atom selections, RMSD, alignment, and periodic boundaries.
- [groan_rs](https://github.com/Ladme/groan_rs). GROMACS-oriented trajectory analysis with selections and geometric analysis.
- [gorder](https://github.com/VachaLab/gorder). Lipid order parameter analysis for MD trajectories.
- [molly](https://github.com/ma3ke/molly). High-performance GROMACS XTC trajectory reader.
- [xdrfile](https://github.com/dnlbauer/xdrfile). Rust bindings for reading and writing XTC and TRR trajectories.
- [minitpr](https://github.com/Ladme/minitpr). GROMACS TPR file parser.

### 3. Protein structure parsing and structural bioinformatics

- [pdbtbx](https://github.com/coudertlab/pdbtbx). PDB and mmCIF structure parsing, inspection, modification, and writing.
- [PDBRust (pdbrust)](https://github.com/search?q=pdbrust&type=repositories). Protein structure analysis including RMSD, alignment, and secondary structure. Repository search link.
- [structscope](https://github.com/Danialgharaie/structscope). PDB/mmCIF/BinaryCIF parsing, structural graphs, SASA, and interactions.
- [folddisco](https://github.com/steineggerlab/folddisco). Search and indexing of discontinuous protein structural motifs.
- [arpeggia](https://github.com/y1zhou/arpeggia). Interatomic interaction analysis.
- [elasticrab](https://github.com/mlund/elasticrab). Protein normal-mode analysis using the anisotropic network model.
- [cgkitten](https://github.com/mlund/cgkitten). Protein coarse-graining and pH titration.
- [BioForge](https://github.com/TKanX/bio-forge). Biomolecular preparation, hydrogen addition, topology construction, and solvation.
- [rotamer](https://github.com/TKanX/rotamer). Protein side-chain coordinate generation.
- [dreid-pack](https://github.com/caltechmsc/dreid-pack). DREIDING-based protein side-chain packing.

### 4. Force fields, molecular mechanics, and structure optimization

- [cheq](https://github.com/caltechmsc/cheq). Geometry-dependent partial charges via charge equilibration.
- [dreid-typer](https://github.com/caltechmsc/dreid-typer). DREIDING atom typing and topology perception.
- [dreid-kernel](https://github.com/caltechmsc/dreid-kernel). DREIDING potential energy and derivative kernels.
- [uff-relax](https://github.com/ForblazeProject/uff-relax). UFF molecular geometry relaxation.
- [sci-form](https://github.com/jigonzalez930209/sci-form). ETKDG-inspired molecular conformer generation.
- [COSMolKit](https://github.com/cosmol-studio/COSMolKit). Conformer generation and UFF/MMFF optimization.

### 5. Cheminformatics and molecular representations

- [gchemol](https://github.com/gchemol/gchemol). Molecular graphs and chemical file I/O.
- [ChemCore](https://github.com/rapodaca/chemcore). Foundational chemical graph and object primitives.
- [COSMolKit](https://github.com/cosmol-studio/COSMolKit). SMILES, SMARTS, fingerprints, descriptors, and conformers.
- [molmap](https://github.com/borodin-chem/molmap). Arena-based molecular data structures.
- [chemrs](https://github.com/bddap-bot/chemrs). SMILES, SMARTS, ring perception, and SDF handling.

### 6. Molecular docking, coarse-graining, and protein interactions

- [gdock](https://github.com/rvhonorato/gdock). Genetic-algorithm protein docking.
- [bentopy](https://github.com/marrink-lab/bentopy). Molecular packing and box construction for coarse-grained systems.
- [cgkitten](https://github.com/mlund/cgkitten). Protein coarse-graining and titration.
- [arpeggia](https://github.com/y1zhou/arpeggia). Protein–ligand and protein–protein interaction analysis.
- [dreid-pack](https://github.com/caltechmsc/dreid-pack). Protein side-chain optimization at molecular interfaces.

### 7. Molecular visualization and interactive structure tools

- [molar_vis](https://github.com/yesint/molar_vis). MolAR-based visualization with trajectories, selections, cartoons, and GPU rendering.
- [Molchanica](https://github.com/David-OConnor/molchanica). Interactive molecular viewer, editor, and simulator.
- [vizmat](https://github.com/rs4rse/vizmat). Molecular and crystal visualization.
- [Rust-mol-viewer](https://github.com/Tyxop/Rust-mol-viewer). GPU-oriented molecular viewer.
- [COSMol-viewer](https://github.com/cosmol-studio/COSMol-viewer). Visualization application in the COSMol ecosystem.

### 8. Quantum chemistry and electronic structure

- [hartree](https://github.com/nmrtist/hartree). Native Rust molecular and periodic electronic-structure software.
- [integral](https://github.com/search?q=rust+integral+quantum+chemistry&type=repositories). Molecular and periodic integral calculations. Repository search link.
- [xcx](https://github.com/search?q=xcx+rust+exchange+correlation&type=repositories). Exchange-correlation calculations. Repository search link.

### 9. Molecular file formats and interoperability

- [molly](https://github.com/ma3ke/molly). GROMACS XTC trajectory decoding.
- [xdrfile](https://github.com/dnlbauer/xdrfile). XTC/TRR trajectory bindings.
- [minitpr](https://github.com/Ladme/minitpr). GROMACS TPR file parsing.
- [MolAR](https://github.com/yesint/molar). PDB, GRO, XYZ, XTC, TRR, and AMBER NetCDF handling.
- [pdbtbx](https://github.com/coudertlab/pdbtbx). PDB and mmCIF handling.
- [structscope](https://github.com/Danialgharaie/structscope). PDB, mmCIF, and BinaryCIF handling.
- [chemfiles-rust](https://github.com/chemfiles/chemfiles.rs). Rust bindings to the C++ Chemfiles molecular I/O library.

### 10. Scientific computing and numerical infrastructure

- [nalgebra](https://github.com/dimforge/nalgebra). Vectors, matrices, transformations, and linear algebra.
- [ndarray](https://github.com/rust-ndarray/ndarray). N-dimensional numerical arrays.
- [faer](https://github.com/sarah-ek/faer-rs). High-performance matrix operations and decompositions.
- [Rayon](https://github.com/rayon-rs/rayon). Data-parallel computation.
- [petgraph](https://github.com/petgraph/petgraph). Graph data structures and algorithms.
- [kiddo](https://github.com/sdd/kiddo). Fast k-d trees and nearest-neighbor search.
- [kdtree](https://github.com/mrhooray/kdtree-rs). Spatial nearest-neighbor indexing.
- [rustfft](https://github.com/ejmahler/RustFFT). Fast Fourier transforms.
- [argmin](https://github.com/argmin-rs/argmin). Numerical optimization.
- [rand](https://github.com/rust-random/rand). Random number generation.
- [wgpu](https://github.com/gfx-rs/wgpu). GPU rendering and computation.
- [burn](https://github.com/tracel-ai/burn). Rust deep learning framework.
- [candle](https://github.com/huggingface/candle). Tensor computing and machine learning.
- [PyO3](https://github.com/PyO3/pyo3). Rust–Python interoperability.
- [maturin](https://github.com/PyO3/maturin). Packaging Rust-based Python extensions.
- [Rust-Bio](https://github.com/rust-bio/rust-bio). Bioinformatics algorithms and data structures.

### 11. Additional research ecosystems

- [LODE](https://lode-org.github.io/index.html). Rare-event simulation and kinetic Monte Carlo ecosystem.
- [Athanor Rust Structural Bio Libraries](https://www.athanorlab.com/rust-tools). Rust tools for structural biology and scientific computing.
- [Rust-Bio](https://github.com/rust-bio). Bioinformatics ecosystem.
- [COSMol ecosystem](https://tools.cosmol.org/ecosystem). Cheminformatics and molecular visualization ecosystem.

*Note: Summary created on the day of the meeting using ChatGPT-6. Projects may appear in multiple categories. Some URLs are repository searches, not verified direct repositories. Descriptions and project status have not been independently reverified.*

