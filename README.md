# CarND-Controls-MPC
Self-Driving Car Engineer Nanodegree Program

---

## The Model

```
      // Recall the equations for the model:
      // x_[t+1] = x[t] + v[t] * cos(psi[t]) * dt
      // y_[t+1] = y[t] + v[t] * sin(psi[t]) * dt
      // psi_[t+1] = psi[t] + v[t] / Lf * delta[t] * dt
      // v_[t+1] = v[t] + a[t] * dt
      // cte[t+1] = f(x[t]) - y[t] + v[t] * sin(epsi[t]) * dt
      // epsi[t+1] = psi[t] - psides[t] + v[t] * delta[t] / Lf * dt
```


## Timestep Length and Elapsed Duration (N & dt)

Higher Timestep Length (N) and & lower Elapsed Duration (dt) are preferd for better results.
The inital Timestep Length (N = 25) was reasonable for my PCs Performance.
The Elapsed Duration (dt) was increased to 0.1 to be equal to the introduced latancy.

## Model Predictive Control with Latency

The Model was very sensitive to errors Phi so i added compensation for the error in Phi based on the introduced latancy to the model.

`           psi -= v * delta / Lf * dt;

The speed was set to a reasonable value to drive savely.