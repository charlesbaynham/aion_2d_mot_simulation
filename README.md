# aion_2d_mot_simulation

AI Model of 2D+ Magneto-Optical Trap

The model consists of:

- A deep neural network to predict the number of vectors
- A CNF-PD (Continuous Normalising Flow with Pre-Diffusion) model, which uses an initial period of diffusion where the data is gradually introduced from static noise, followed by standard CNF training with learning rate decay and early stopping rounds

## How to Run

1. Set the parameters in the `params.json` file.
2. Execute the `sim.py` script.

## Capabilities

- The model can only capture a pipe with up to 11mm on the x-axis and 7.75mm on the y-axis, the data is clipped to set pipe dimensions in params.json
- Currently the model is trained to predict data at the entrance to the pipe.
- The model is trained on data corresponding to the following parameter ranges:

| Symbol | Parameter                     | Minimum Value | Maximum Value | Units |
| ------ | ----------------------------- | ------------- | ------------- | ------ |
| $\delta_c$ | Cooling Beam Detuning         | -250          | 0             | MHz   |
| $P_{c}$ | Cooling Beam Power            | 50            | 350           | mW    |
| $w_c$ | Cooling Beam Waist           | 7             | 15            | mm    |
| $\delta_p$ | Push Beam Detuning            | -350          | 0             | MHz   |
| $P_{p}$ | Push Beam Power               | 0             | 20            | mW    |
| $w_p$ | Push Beam Waist              | 0             | 3             | mm    |
| $d_{p}$ | Push Beam Offset              | 0             | 5             | mm    |
| $\nabla B$ | Quadrupole Gradient           | 0             | 100           | G/cm  |
| $B_{v}$ | Vertical Bias Field           | -20           | 20            | G     |

Ensure that the values of the parameters are within these ranges to ensure stability. Going beyond these ranges may give unpredictable results.
