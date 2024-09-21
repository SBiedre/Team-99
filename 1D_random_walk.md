1D random walk
```py
import numpy as np
import random
import matplotlib.pyplot as plt

n=10000
x = np.zeros(n)

# Variable to count the number of 'up' steps
up_steps = 0

for i in range(1,n):
    step = random.choice([-1, 1])  # Choose randomly between -1 (down) and +1 (up)
    x[i] = x[i-1] + step  # Update the position
    
    if step == 1:
        up_steps += 1

# Plot the 1D random walk (just x-axis)
plt.plot(x, label="Random Walk")
plt.title(f'Random Walk of n={n} steps.')
plt.xlabel("Step Number")
plt.ylabel("Position (x)")
plt.legend()
plt.show()

print(f'Number of up steps: {up_steps}')
```
