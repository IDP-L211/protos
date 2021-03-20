# Estimation of error in IR sensor
Data:
```python
data = [
	(0,    0,     0),
	(0.1,  2.31, 0.05),
	(0.15, 2.75, 0.05),
	(0.2,  2.53, 0.05),
	(0.3,  1.98, 0.05),
	(0.4,  1.54, 0.05),
	(0.5,  1.23, 0.05),
	(0.6,  1.05, 0.05),
	(0.7,  0.90, 0.05),
	(0.8,  0.81, 0.05),
	(0.9,  0.72, 0.05),
	(1.0,  0.65, 0.05),
	(1.1,  0.60, 0.05),
	(1.2,  0.55, 0.05),
	(1.3,  0.52, 0.05),
	(1.4,  0.48, 0.05),
	(1.5,  0.45, 0.05),
]
```
Plotting
```python
import matplotlib.pyplot as plt
plt.plot(*list(zip(*data))[:2]) # Curve
plt.plot(*list(zip(*map(
	lambda x: (x[0], x[1] + x[2]),
	data
))), 'C1--')

plt.plot(*list(zip(*map(
	lambda x: (x[0], x[1] - x[2]),
	data
))), 'C1--', label='Error bars given $\pm50mV$ uncertainty')

# Minimum acceptable value
plt.plot([data[0][0], data[-1][0]], 2*[data[-1][1] + data[-1][2]], 'C5')

# This one is manual
plt.plot([1.2, 1.2], [0, 0.55], 'C5')

plt.xlabel("Distance to IR sensor (m)")
plt.ylabel("Sensor output (V)")

plt.legend()
plt.savefig('ir_error.pdf', bbox_inches='tight')

```
![IR Error](ir_error.pdf)

I used [vim-venus](https://github.com/tim-clifford/vim-venus) for this.
Totally shameless plug.
