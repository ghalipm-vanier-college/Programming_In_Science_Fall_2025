```python
# import for colormaps
from matplotlib import cm
import matplotlib.pyplot as plt
import numpy as np

# x=np.linspace(-10,10, num=100)
# y=np.linspace(-10,10, num=100)
h=0.1
x=np.arange(-20,20+h, h)
y=np.arange(-20,20+h, h)

x, y = np.meshgrid(x, y)

z = np.exp(-0.01*x**2-0.01*y**2)

fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
ax.plot_surface(x,y,z, cmap=cm.jet)
plt.show()
     


# Animation:
import numpy as np
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation
from IPython.display import HTML

# Ensure ffmpeg is installed
!apt-get install ffmpeg

# Data
h = 0.01
n=100
```python
a=2
# x = np.arange(-a, a + h, h)
x=np.linspace(-a,a,n)
# y = x**2
y=2*np.sin(4*x)

# Plot setup
fig, ax = plt.subplots(figsize=(8, 6))
ax.set_xlim(-a, a) # view length can be adjusted
ax.set_ylim(-a, a) # view height has to be adjusted
ax.set_xlabel('x')
ax.set_ylabel('y')
ax.set_title('Animation of y ')
ax.grid(True)

# Initialize line
line, = ax.plot([], [], 'b-', label='y ')
ax.legend()

# Initialization
def init():
    line.set_data([], [])
    return line

# Update function
def update(frame):
    line.set_data(x[:frame], y[:frame])
    return line

# Create animation
ani = FuncAnimation(fig, update, frames=len(x), init_func=init, blit=False, interval=n)

# Display
plt.close()
HTML(ani.to_jshtml())
```     

