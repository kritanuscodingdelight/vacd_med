# VACD-MED

## Overview

Trains a model to decide when to abstain from answering a clinical question about an adverse drug reaction, grounded in measurable evidence gaps.

## Pipeline

**Base VACD-MED** — Frozen BiomedBERT text encoder and ResNet-50 image encoder. A gap vector (need minus available evidence) feeds an Alignment Scorer producing a score in [0,1]. A learnable threshold determines abstention.

**VACD-MED + GRPO** — Fine-tunes the model treating abstention as a policy decision with a reward combining correctness, calibration, and confidence.

**FaithGen** — T5 model generating natural language justifications, evaluated with BERTScore and NLI faithfulness.
