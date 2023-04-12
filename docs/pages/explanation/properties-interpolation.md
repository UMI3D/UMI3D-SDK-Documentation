# Interpolation

To have a smoothing effect when changing an object properties it is possible to ask for browsers to interpolate the properties values. First, a `StartInterpolation` Operation should be sent. And when the environment decide to stop the smoothing effect, a `StopInterpolation` Operation should be sent.

![image.png](./img/exp-interpolation.png)

It also greatly diminishes the pressure on the bandwitdh.

![image.png](./img/exp-interpolation-graph.png)