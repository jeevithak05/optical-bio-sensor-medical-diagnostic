# optical-bio-sensor-medical-diagnostic
An optical biosensor is a device that detects biological analytes (like glucose, proteins, or pathogens) using an optical transduction method. These biosensors are crucial in non-invasive and real-time medical diagnostics.
import numpy as np
import matplotlib.pyplot as plt

# Simulate concentration of biomolecule (e.g., glucose) in mg/dL
concentration = np.linspace(0, 300, 100)  # 0 to 300 mg/dL

# Simulate optical absorbance using Beer-Lambert Law
# A = ε * c * l
# Assume ε (molar absorptivity) = 0.01, l (path length) = 1 cm
epsilon = 0.01
path_length = 1  # cm
absorbance = epsilon * concentration * path_length

# Convert absorbance to voltage output from photodiode
# Simulated response: V = Vmax * (1 - 10^(-A))
Vmax = 5.0  # Max voltage
voltage_output = Vmax * (1 - 10 ** (-absorbance))

# Plot the response
plt.figure(figsize=(10, 6))
plt.plot(concentration, voltage_output, label='Sensor Output (V)')
plt.xlabel("Biomolecule Concentration (mg/dL)")
plt.ylabel("Photodiode Voltage Output (V)")
plt.title("Optical Biosensor Response Curve")
plt.grid(True)
plt.legend()
plt.show()
