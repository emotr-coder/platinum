import time
import pygame
import random
import math
import tkinter as tk
from tkinter import messagebox
import pygame
import math
import pygame
import math
import random

import pygame
import math
root = tk.Tk()
root.withdraw()  # Hide main window

# Ask the user
response = messagebox.askyesno("Confirmation", "run?")
response = messagebox.showinfo("PLATINUM", "PLATINUM INFECTED YOU RESS IN PISS")
if response:
    print("You clicked Yes.")
else:
    print("You clicked No.")
    exit()  # Or use quit()
import pygame
import math

# Initialize pygame
pygame.init()

# Get the screen resolution
info = pygame.display.Info()
width, height = info.current_w, info.current_h  # Set to screen's width and height

# Create a fullscreen window
screen = pygame.display.set_mode((width, height), pygame.FULLSCREEN)
pygame.display.set_caption('Tunneling Effect on Screenshot')

# Colors
BLACK = (0, 0, 0)

# Tunnel parameters
num_lines = 100  # Number of lines in the tunnel
speed = 0.1      # Speed of tunnel zoom
angle_speed = 0.05  # Speed of angle rotation for tunnel

# Take screenshot function
def take_screenshot():
    # Capture the current screen to a new surface
    return pygame.display.get_surface().copy()

# Game loop
running = True
clock = pygame.time.Clock()

# Initial angle
angle = 0

# Capture the initial screenshot
screenshot = take_screenshot()

while running:
    screen.fill(BLACK)  # Clear the screen with black

    # Apply the tunneling effect to the screenshot
    for i in range(num_lines):
        # Calculate the "z" depth and scale based on the line number
        z = (i - num_lines / 2) * speed
        
        # Calculate the x and y coordinates for the line
        x = math.cos(angle + z) * z
        y = math.sin(angle + z) * z
        
        # Scale the lines to make them bigger as they move toward the viewer
        scale = width / (z + width / 2)
        
        # Scale coordinates by the calculated scale
        x_screen = int(width / 2 + x * scale)
        y_screen = int(height / 2 + y * scale)
        
        # Ensure coordinates are within the bounds of the screenshot
        x_screen = max(0, min(x_screen, width - 1))
        y_screen = max(0, min(y_screen, height - 1))

        # Get the color from the screenshot at the scaled coordinates
        color = screenshot.get_at((x_screen, y_screen))  # Using correct tuple syntax

        # Draw the line with the color from the screenshot
        pygame.draw.line(screen, color, (width // 2, height // 2), (x_screen, y_screen), 2)

    # Rotate the tunnel effect
    angle += angle_speed

    # Handle events (close window)
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    pygame.display.flip()  # Update the screen
    clock.tick(60)  # 60 FPS

pygame.quit()



# initialize pygame mixer (sound)
pygame.mixer.init(frequency=8000, size=-8, channels=1)

# 🎵 Your bytebeat formulas
def formula_chill(t):
    return ((t >> 4 | t >> 5) * 3) & 0xFF

def formula_glitch(t):
    return (t * (t >> 5 | t >> 8)) & 0xFF

def formula_machine(t):
    return (t * 9 & t >> 4 | t * 5 & t >> 7) & 0xFF

def formula_lalala(t):
    return (t >> 6 | t | t >> 9) & 0xFF

# 🎼 List of formulas
formulas = [formula_chill, formula_glitch, formula_machine]

# 🔊 Function to build sound
def generate_sound(formula, duration=4, sample_rate=8000):
    samples = bytearray()
    for t in range(duration * sample_rate):
        samples.append(formula(t))
    return pygame.mixer.Sound(buffer=bytes(samples))

# 🌐 Settings
duration = 10  # seconds per formula
index = 0     # current formula index



try:
    while True:
        current_formula = formulas[index]
        sound = generate_sound(current_formula, duration)
        sound.play()

        time.sleep(duration)

        index = (index + 1) % len(formulas)  # cycle through 0 → 1 → 2 → 0...
except KeyboardInterrupt:
    print("\nStopped.")
