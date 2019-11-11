# DCTRHunting

This repository explores the possibility of applying the [DCTR technique](https://github.com/bnachman/DCTR) to anomaly detection.  The setting is that there is some feature _m_ where the signal is expected to be resonant.  There are other features _x_ that can be used to enhance signal over background.  In the [CWoLa hunting methodology](https://arxiv.org/abs/1805.02664), one can only use features _x_ that don't sculpt a bump (a looser requirement than being independent from _m_, but clearly that would be sufficient); then a parameteric fit based on the sidebands is used to estimate the background in the signal region.  In this new approach, a DCTR model is used to reweight simulation to data in away from the signal region.  This model is parameterized in _m_ and then interpolated to the signal region.  The reweighted simulation in the signal region can then be used to make a classifier (using _x_) as well as estimate the background.  There is no need for a sideband fit if the reweighting works well.

## Notebooks

We provide a few example notebook to illustrate how DCTR Hunting works

### Simple Gaussian Example
To illustrate the basic idea behind DCTR hunting, we provide
- A basic example just using a Gaussian distribution `./Toy.ipynb`

### High Energy Physics Examples
_To be filled in_
- Based on the [LHCO2020 dataset](https://indico.cern.ch/event/809820/page/16782-lhcolympics2020).
