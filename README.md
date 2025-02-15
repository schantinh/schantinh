import numpy as np
import matplotlib.pyplot as plt
import matplotlib.animation as animation

# Heart shape function
def heart_shape(t):
    x = 16 * np.sin(t) ** 3
    y = 13 * np.cos(t) - 5 * np.cos(2 * t) - 2 * np.cos(3 * t) - np.cos(4 * t)
    return x, y

# Flower shape function
def flower_shape(t, petals=6):
    r = 10 + 3 * np.sin(petals * t)
    x = r * np.cos(t)
    y = r * np.sin(t)
    return x, y

# Create figure and axis
fig, ax = plt.subplots()
ax.set_xlim(-20, 20)
ax.set_ylim(-20, 20)
ax.set_aspect('equal')
ax.axis('off')

# Initialize heart and flower plots
heart_t = np.linspace(0, 2 * np.pi, 1000)
heart_x, heart_y = heart_shape(heart_t)
flower_t = np.linspace(0, 2 * np.pi, 1000)
flower_x, flower_y = flower_shape(flower_t)

heart, = ax.plot([], [], 'r-', lw=2)
flower, = ax.plot([], [], 'g-', lw=2)

# Animation update function
def update(frame):
    # Update heart position
    heart.set_data(heart_x + frame, heart_y + frame)
    
    # Update flower bloom
    petal_count = 6 + frame // 10
    flower_x, flower_y = flower_shape(flower_t, petals=petal_count)
    flower.set_data(flower_x, flower_y)
    
    return heart, flower

# Create animation
ani = animation.FuncAnimation(fig, update, frames=range(100), interval=100, blit=True)

# Save or show the animation
# ani.save('heart_flower_animation.gif', writer='imagemagick')
plt.show()
