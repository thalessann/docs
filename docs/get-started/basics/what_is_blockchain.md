import numpy as np
import matplotlib.pyplot as plt

# Definindo os parâmetros
A = 0.04  # Amplitude
omega = 2.15  # Frequência angular
phi = 0  # Fase inicial

# Função para posição
def position(t):
    return A * np.cos(omega * t)

# Função para velocidade
def velocity(t):
    return -A * omega * np.sin(omega * t)

# Função para aceleração
def acceleration(t):
    return -A * (omega ** 2) * np.cos(omega * t)

# Criação do vetor de tempo
t = np.linspace(0, 2*np.pi/omega, 1000)

# Plotagem dos gráficos
plt.figure(figsize=(12, 8))

plt.subplot(3, 1, 1)
plt.plot(t, position(t))
plt.title('Gráfico da posição em função do tempo')
plt.xlabel('Tempo (s)')
plt.ylabel('Posição (m)')

plt.subplot(3, 1, 2)
plt.plot(t, velocity(t))
plt.title('Gráfico da velocidade em função do tempo')
plt.xlabel('Tempo (s)')
plt.ylabel('Velocidade (m/s)')

plt.subplot(3, 1, 3)
plt.plot(t, acceleration(t))
plt.title('Gráfico da aceleração em função do tempo')
plt.xlabel('Tempo (s)')
plt.ylabel('Aceleração (m/s^2)')

plt.tight_layout()
plt.show()
