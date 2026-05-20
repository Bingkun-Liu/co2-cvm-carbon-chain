# AI Carbon Chain Prediction with CVM

This repository archives and reconstructs an undergraduate AI research project
on predicting product-level carbon chains from object data.

The project explored how computer vision, graph-based production-chain
modeling, and sequence-to-sequence learning could be combined to estimate
carbon values for physical objects. The central AI idea was to turn a product's
materials, components, machines, and manufacturing steps into a machine-readable
symbol sequence, then train a model to map that source sequence to CO2 /
carbon-value targets.

## AI Focus

This project framed carbon accounting as a representation-learning and
sequence-prediction problem:

- Computer vision identifies an object and its likely components.
- A structured production-chain graph represents the object's life cycle.
- Graph nodes are encoded into symbolic sequences.
- A seq2seq model learns relationships between production-chain symbols and
  carbon-value outputs.
- The prediction can support an app or interface for carbon-emission estimation.

## Reconstructed Goal

Given a product image or object description, the system aimed to:

1. Use image classification or object detection to identify the object.
2. Reconstruct the object's production chain, including materials, machines,
   intermediate objects, and distribution steps.
3. Encode the production chain as symbolic source sequences suitable for ML.
4. Use a seq2seq model to predict target sequences representing CO2 values or
   carbon-flow information.
5. Provide the resulting carbon-chain estimate to an application interface for
   carbon-emission estimation and decision support.

## AI Pipeline

```text
input image / object description
-> image classification or object detection
-> component, material, and process recognition
-> object IDs in a database / model card
-> symbolic graph / production-chain representation
-> seq2seq model for CO2 / carbon-value prediction
-> carbon-chain estimate for a user-facing tool
```

## Visual Walkthrough

### 1. AI System Structure

![Process steps from image data to symbolic sequence prediction](assets/figures/image1.png)

The system starts with image data about an object. The object passes through
classification, detailed recognition, database lookup, conversion from object
IDs to symbols, and finally symbol-sequence prediction. This diagram is the
clearest overview of the proposed AI pipeline.

### 2. Structured Data for the Model

![Yakult manufacturing process with graph overlay](assets/figures/image4.png)

One example reconstructed a Yakult manufacturing process from a production
diagram. Nodes represent materials, machines, tanks, pumps, filters, and
intermediate production steps. The goal was to turn a product diagram into a
structured graph that a model could consume.

### 3. Carbon-Value Graph Representation

![Circular CO2 accounting graph](assets/figures/image2.png)

The reconstructed production network could then be represented as a CVM /
Circularity Accounting Model graph. In this representation, product inputs,
process steps, and CO2 values become connected nodes in a carbon-chain model.
This provided the target domain for carbon-flow prediction.

### 4. Seq2Seq Training Target

![Object symbols mapped to CO2 values](assets/figures/image6.png)

The training representation followed a seq2seq pattern: source-side object or
production-chain symbols were mapped to target-side CO2 values or carbon-flow
symbols. This matches the recovered server-side dataset names:

```text
sources.txt
targets.txt
vocab.sources.txt
vocab.targets.txt
```

## Original Project Concepts

- CO2 sequestration networks and vectors
- Circularity Accounting Model / CVM
- Consumption vectors
- Supply-chain and disposal-chain encoding
- Object IDs to symbols
- Symbol-sequence prediction
- Source-to-target sequence learning
- Carbon-flow and carbon-value estimation
- Computer vision for object and component recognition
- Seq2seq modeling for carbon-chain prediction

## Examples in the Notes

The original notes include two main example domains:

- Blue jeans: denim, dye, zipper, buttons, sewing machines, cutting machines,
  pressing machines, and related production steps.
- Yakult manufacturing: milk, sugar, water, tanks, filters, pumps,
  homogenizers, packaging, storage, and distribution.

## Recovered Materials

- `docs/originals/co2_web_design.docx`: original Word export with project notes.
- `docs/originals/co2_web_design.pages`: original Pages document.
- `docs/originals/CO2-CV.pages`: later Pages note summarizing the machine
  learning direction.
- `assets/figures/`: extracted diagrams and document previews.
- `docs/notes/project-reconstruction.md`: a reconstructed explanation of what
  the project was doing.

## Historical Context

The recovered terminal screenshots suggest that training data was once stored
on a university-network-accessible server under a path similar to:

```text
~/2022s2s/seq2seq/nmt_data/CVM/train
```

The files shown in the screenshot included:

```text
sources.txt
targets.txt
vocab.sources.txt
vocab.targets.txt
original_source.txt
original_targets.txt
```

Those data files are not included here because the server required access to
the undergraduate university network and the original notes did not contain the
full dataset.

## Status

This repository is an archival reconstruction rather than a runnable training
pipeline. It preserves the project documents, diagrams, and inferred system
design so the work can be referenced, extended, or rewritten in a modern form.
