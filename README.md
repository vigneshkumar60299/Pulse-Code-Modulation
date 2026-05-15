# Pulse-Code-Modulation
# Aim
Write a simple Python program for the modulation and demodulation of PCM, and DM.
# Tools required
# Program
```
import numpy as np
import matplotlib.pyplot as plt

fs, f, T, L = 5000, 50, 0.1, 16
t = np.linspace(0, T, int(fs*T), False)

msg = np.sin(2*np.pi*f*t)
clk = np.sign(np.sin(2*np.pi*200*t))

step = (msg.max()-msg.min())/L
q_msg = np.round(msg/step)*step

plt.figure(figsize=(10,8))

plt.subplot(4,1,1); plt.plot(t,msg); plt.title("Analog Message"); plt.grid()
plt.subplot(4,1,2); plt.plot(t,clk); plt.title("Clock Signal"); plt.grid()
plt.subplot(4,1,3); plt.step(t,q_msg); plt.title("PCM Signal"); plt.grid()
plt.subplot(4,1,4); plt.plot(t,q_msg,'--'); plt.title("PCM Demodulation"); plt.grid()

plt.tight_layout()
plt.show()
```
# Output Waveform

<img width="990" height="790" alt="image" src="https://github.com/user-attachments/assets/14f71f6c-58e3-4ab5-8c45-bc3c3589cbb2" />


# Results

<img width="990" height="790" alt="image" src="https://github.com/user-attachments/assets/b018f516-5154-43a2-8e38-e852d71abd0c" />

# Hardware experiment output waveform.
