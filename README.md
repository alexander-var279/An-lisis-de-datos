# Analisis-de-datos
Repositorio #1
# Ejemplo introductorio con Python

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# -----------------------------
# 1. Crear un DataFrame simulado
# -----------------------------
data = {
    "Año": [2018, 2019, 2020, 2021, 2022],
    "PIB": [350, 370, 340, 390, 410],  # en miles de millones
    "Desempleo": [9.5, 9.0, 12.0, 8.5, 7.8]  # en porcentaje
}

df = pd.DataFrame(data)

print("Datos económicos:")
print(df)

# -----------------------------
# 2. Estadísticas descriptivas
# -----------------------------
print("\nEstadísticas descriptivas:")
print(df.describe())

# -----------------------------
# 3. Correlación PIB vs Desempleo
# -----------------------------
correlacion = df["PIB"].corr(df["Desempleo"])
print(f"\nCorrelación PIB vs Desempleo: {correlacion:.2f}")

# -----------------------------
# 4. Visualización
# -----------------------------
plt.figure(figsize=(8,5))

# Gráfico de PIB
plt.subplot(1,2,1)
plt.plot(df["Año"], df["PIB"], marker="o", color="blue")
plt.title("PIB por Año")
plt.xlabel("Año")
plt.ylabel("PIB (miles de millones)")

# Gráfico de Desempleo
plt.subplot(1,2,2)
plt.plot(df["Año"], df["Desempleo"], marker="o", color="red")
plt.title("Desempleo por Año")
plt.xlabel("Año")
plt.ylabel("Tasa de desempleo (%)")

plt.tight_layout()
plt.show()
