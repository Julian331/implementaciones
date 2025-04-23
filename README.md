### 🔷 **1. Fórmulas del Modelo M/M/c**

**Parámetros básicos:**
- \( \lambda \): tasa de llegada (clientes por unidad de tiempo)
- \( \mu \): tasa de servicio (clientes atendidos por cada servidor por unidad de tiempo)
- \( c \): número de servidores
- \( \rho = \frac{\lambda}{c\mu} \): **factor de utilización** del sistema

---

#### 🔹 Fórmula de \( P_0 \): probabilidad de que no haya clientes en el sistema

\[ P_0 = \left[ \sum_{n=0}^{c-1} \frac{(\lambda/\mu)^n}{n!} + \frac{(\lambda/\mu)^c}{c! (1 - \rho)} \right]^{-1} \]

---

#### 🔹 Longitud promedio en la cola (Lq):

\[ L_q = \frac{(\lambda/\mu)^c \cdot \rho}{c! (1 - \rho)^2} \cdot P_0 \]

---

#### 🔹 Tiempo promedio en cola (Wq):

\[ W_q = \frac{L_q}{\lambda} \]

---

#### 🔹 Tiempo promedio en el sistema (W):

\[ W = W_q + \frac{1}{\mu} \]

---

#### 🔹 Número promedio de clientes en el sistema (L):

\[ L = \lambda \cdot W \]

---

### 🔷 **2. Análisis numérico para diferentes valores de c**

---

### ✅ **Caso 1: c = 1 servidor**
- \( \rho = \frac{1}{1} = 1 \)

Este caso representa una **utilización del 100%**, lo que significa que el sistema está **saturado**.  
Como \( \rho = 1 \), **la fórmula de \( P_0 \) no converge**, y el sistema se considera **inestable**:  
- La fila crecerá indefinidamente  
- \( L_q \to \infty \), \( W_q \to \infty \)

---

### ✅ **Caso 2: c = 2 servidores**
- \( \rho = \frac{1}{2} = 0.5 \)

**Paso 1: Calcular \( P_0 \)**

\[ P_0 = \left[ \frac{(1)^0}{0!} + \frac{(1)^1}{1!} + \frac{(1)^2}{2! (1 - 0.5)} \right]^{-1} = \left[ 1 + 1 + \frac{1}{2 \cdot 0.5} \right]^{-1} = \left[ 1 + 1 + 1 \right]^{-1} = \frac{1}{3} \]

**Paso 2: Calcular \( L_q \)**

\[ L_q = \frac{(1)^2 \cdot 0.5}{2! \cdot (1 - 0.5)^2} \cdot \frac{1}{3} = \frac{1 \cdot 0.5}{2 \cdot 0.25} \cdot \frac{1}{3} = \frac{0.5}{0.5} \cdot \frac{1}{3} = 1 \cdot \frac{1}{3} = \frac{1}{3} \]

**Wq = Lq / λ = 1/3**,  
**W = 1/3 + 1 = 4/3**,  
**L = λ * W = 1 * 4/3 = 4/3**

---

### ✅ **Caso 3: c = 3 servidores**
- \( \rho = \frac{1}{3} \approx 0.333 \)

**Paso 1: Calcular \( P_0 \)**

\[ P_0 = \left[ \sum_{n=0}^{2} \frac{1^n}{n!} + \frac{1^3}{3!(1 - 1/3)} \right]^{-1} = \left[ 1 + 1 + 0.5 + \frac{1}{6 \cdot (2/3)} \right]^{-1} = \left[ 2.5 + \frac{1}{4} \right]^{-1} = \left[ 2.75 \right]^{-1} \approx 0.3636 \]

**Paso 2: \( L_q \)**

\[ L_q = \frac{1^3 \cdot (1/3)}{3! \cdot (1 - 1/3)^2} \cdot 0.3636 = \frac{1/3}{6 \cdot (4/9)} \cdot 0.3636 = \frac{1/3}{2.6667} \cdot 0.3636 \approx 0.125 \cdot 0.3636 \approx 0.0455 \]

**Wq ≈ 0.0455**,  
**W ≈ 1.0455**,  
**L ≈ 1.0455**

---

### ✅ **Caso 4: c = 4 servidores**
- \( \rho = \frac{1}{4} = 0.25 \)

\[ P_0 \approx \left[ 1 + 1 + 0.5 + \frac{1}{6} + \frac{1}{24 \cdot (0.75)} \right]^{-1} = \left[ 2.5 + \frac{1}{18} \right]^{-1} \approx 0.5048 \]

\[ L_q \approx \frac{1^4 \cdot 0.25}{4! \cdot (0.75)^2} \cdot 0.5048 = \frac{0.25}{24 \cdot 0.5625} \cdot 0.5048 = \frac{0.25}{13.5} \cdot 0.5048 \approx 0.0185 \cdot 0.5048 \approx 0.0094 \]

**Wq ≈ 0.0094**,  
**W ≈ 1.0094**,  
**L ≈ 1.0094**

---

### ✅ **Caso 5: c = 5 servidores**
- \( \rho = \frac{1}{5} = 0.2 \)

\[ P_0 \approx \left[ \sum_{n=0}^{4} \frac{1^n}{n!} + \frac{1^5}{5!(1 - 0.2)} \right]^{-1} = \left[ 1 + 1 + 0.5 + 0.1667 + 0.0417 + \frac{1}{120 \cdot 0.8} \right]^{-1} = \left[ 2.7084 + 0.0104 \right]^{-1} \approx 0.3608 \]

\[ L_q = \frac{1^5 \cdot 0.2}{5! \cdot (0.8)^2} \cdot 0.3608 = \frac{0.2}{120 \cdot 0.64} \cdot 0.3608 = \frac{0.2}{76.8} \cdot 0.3608 \approx 0.0026 \cdot 0.3608 \approx 0.00094 \]

**Wq ≈ 0.00094**,  
**W ≈ 1.00094**,  
**L ≈ 1.00094**

---

### 🔷 **Conclusiones**

- Cuando \( c = 1 \), el sistema colapsa si \( \lambda = \mu \), ya que no hay capacidad de respuesta adicional.
- A medida que aumentas los servidores, el sistema se estabiliza rápidamente y los tiempos de espera bajan casi a cero.
- Esto **coincide con la simulación de NetLogo**, donde al aumentar \( c \), la fila se despeja casi completamente.
