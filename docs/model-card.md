# Model Card (Skeleton Template)

> This is a template to be filled in once the scoring engine is built. See
> [`models/scoring-engine/model_card.md`](../models/scoring-engine/model_card.md)
> for the model-specific stub.

## Model purpose

TBD — describe what the model estimates (e.g. a fused stress/focus/fatigue
state score) and its intended use within Seventh Sense.

## Inputs

TBD — list the derived feature frames consumed (see
[`shared/schemas/`](../shared/schemas/)), e.g. watch feature frame, RB3
context frame, phone context frame.

## Outputs

TBD — describe the output representation (e.g. a bounded score per
dimension, or a discrete state label) and how it maps to an intervention
decision.

## Training data

TBD — describe data provenance once training begins. No real personal
identifying data should be used without documented consent.

## Known limitations

TBD — to be filled in after initial evaluation (e.g. sensitivity to missing
devices, cold-start behavior, demographic coverage of any training data).

## Non-medical-use disclaimer

This model does not diagnose, treat, or claim to detect any medical or
mental health condition. It produces a wellness/productivity signal only,
for the user's own personal use, and is not a substitute for professional
medical advice.
