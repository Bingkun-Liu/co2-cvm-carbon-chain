# Project Reconstruction

## Short Description

This project investigated whether a product's carbon chain could be predicted
from object-level information. It combined ideas from computer vision,
production-chain modeling, graph representation, and sequence-to-sequence
learning.

The project used CVM / Circularity Accounting Model diagrams to represent the
life cycle of an object. A product's inputs, materials, machines, processing
steps, packaging, and distribution steps were encoded as graph nodes. Those
nodes were then transformed into symbolic sequences that could be used as
training data for a seq2seq model.

## What the Model Was Trying to Learn

The source side of the dataset appears to have represented object symbols or
production-chain symbols. The target side appears to have represented carbon
values, carbon-flow states, or CVM-derived target symbols.

In simplified form:

```text
source: object / production-chain symbol sequence
target: CO2 value / carbon-flow symbol sequence
```

An example diagram from the original document labels the source side as
"object symbol" and the target side as "CO2 Value".

## Larger System Idea

The later `CO2-CV.pages` note suggests a broader AI system:

1. Use ImageNet, SSD, or an autoencoder model for object recognition.
2. Convert image-recognition outputs into database or model-card entries.
3. Rebuild the CVM / production-chain graph for the object.
4. Use seq2seq to process the carbon-value production chain.
5. Return a prediction for another object or provide a result to a user-facing
   carbon-emission application.

The note also mentions a possible later direction: replacing or extending parts
of the autoencoder / mapping pipeline with diffusion models, including a more
general biophysics or molecular-transformation setting.

## Interpreted Contribution

The work was not just data entry. It involved:

- Designing a representation for production-chain and disposal-chain data.
- Converting real product processes into graph structures.
- Mapping graph nodes into stable symbolic sequences.
- Preparing seq2seq-style training data.
- Connecting carbon accounting with machine-learning prediction.
- Thinking about how the output could support an interactive app for estimating
  and manipulating carbon emissions.

## Known Examples

### Blue Jeans

The blue-jeans example includes materials and manufacturing components such as:

- cotton / denim
- dye
- zipper
- buttons
- sewing machine
- cutting machine
- pressing machine
- loom and processing machinery

### Yakult

The Yakult example includes production and packaging components such as:

- milk
- sugar
- water
- preparation tanks
- balance tanks
- HTST units
- pumps and filters
- homogenizers
- bottle selection
- label printing
- packaging
- cold storage and distribution

## Missing Original Data

The terminal screenshots suggest that the seq2seq training data was stored on a
remote university server. The visible path was:

```text
~/2022s2s/seq2seq/nmt_data/CVM/train
```

The visible file names were:

```text
sources.txt
targets.txt
vocab.sources.txt
vocab.targets.txt
original_source.txt
original_targets.txt
```

Those files are not currently recovered in this repository.
