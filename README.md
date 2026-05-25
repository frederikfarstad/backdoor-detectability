# Non-Data-Poisoning Backdoor Attacks & Detection

Master's thesis on undetectability of architectural and weight-manipulation
backdoors in neural networks. The repository collects reference
re-implementations of published non–data-poisoning attacks alongside a
unified detection harness that runs every detector against every attack.

## What's in this repo

```
.
├── Attacks/                # One subfolder per published attack
├── BaselineModels/         # Clean ResNet baseline helper code 
├── Datasets/               # Datasets
└── Detection/              # Modular detection framework (see Detection/README.md)
```

Each folder under `Attacks/` is a near-verbatim copy of the upstream attack
repository with minimal modifications, used to produce the backdoored
checkpoints the detection suite then analyses.

## Getting started

Detection is the main entry point. The CLI runs every configured
attack × detector combination and writes JSON/CSV/LaTeX results:

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r Detection/requirements.txt
python -m Detection.run --config Detection/configs/default.yaml --device cuda
```

See [Detection/README.md](Detection/README.md) for full configuration, the
list of supported attacks/detectors, and instructions for adding new
adapters or detection methods.

Reproducing a single attack from scratch requires that attack's own
environment — see the README in each `Attacks/<attack>/` folder for the
upstream's setup instructions.

## Citing this work

```bibtex
@mastersthesis{farstad_austad_2026_nondatapoisoning,
  author = {Farstad, Frederik Andreas Brunvoll and Austad, Lisa Marie F{\o}lstad},
  title  = {Non-Data-Poisoning Backdoor Attacks \& Detection},
  school = {Norwegian University of Science and Technology (NTNU)},
  year   = {2026},
  month  = jun,
  type   = {Master's thesis}
}
```

## License

MIT — see `LICENSE`.
