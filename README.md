# Netgear-GS305E
Netgear GS305E is a managed Gigabit Ethernet switch with basic Layer 2 features, perfect for small office or home networks. This repository will collect documentation, configuration guides, firmware updates, scripts, and troubleshooting resources for the GS305E model.
# 🛠️ Netgear GS305E – Configuración Final (Port-Based VLAN)

**Última actualización:** 2025-11-19  
**Autor:** Gabe  

Este documento describe la configuración final del switch **Netgear GS305E**, utilizado como switch administrado con VLANs port-based y QoS para separar equipos domésticos vs. equipo de trabajo.

---

## 📘 1. Información General del Switch

| Parámetro | Valor |
|----------|--------|
| Modelo | Netgear GS305E |
| Modo VLAN | Port-Based (Basic) |
| QoS | Enabled |
| DHCP | Disabled |
| Dirección IP | `192.168.0.50` |
| Subnet Mask | `255.255.255.0` |
| Gateway | `192.168.0.1` |

---

## 🔀 2. VLANs Configuradas (Port-Based)

### **VLAN Group 1 – Red principal (LAN doméstica)**

| Puerto | Estado |
|--------|--------|
| 1 | Miembro |
| 2 | Miembro |
| 3 | Miembro |

### **VLAN Group 2 – Red aislada (equipo de trabajo)**

| Puerto | Estado |
|--------|--------|
| 4 | Miembro |
| 5 | Miembro |

---

## 🧩 3. QoS (Prioridades 802.1p)

| Puerto | Prioridad | Notas |
|--------|-----------|--------|
| **1** | Medium | Uplink al Festa FR205 |
| **2** | Medium | Motorola Satellite |
| **3** | Medium | Laptop Ubuntu |
| **4** | Medium | Raspberry Pi |
| **5** | **High** | Laptop del trabajo (máxima prioridad) |

---

## 📌 4. Asignación Final de Puertos

| Puerto | Dispositivo | VLAN | Prioridad | Comentarios |
|--------|-------------|-------|-----------|-------------|
| **1** | Uplink Festa FR205 | VLAN 1 | Medium | Conexión principal hacia Internet |
| **2** | Motorola Satellite | VLAN 1 | Medium | WiFi Mesh |
| **3** | Laptop Ubuntu | VLAN 1 | Medium | Equipo personal |
| **4** | Raspberry Pi | VLAN 2 | Medium | Aislada |
| **5** | Laptop Trabajo | VLAN 2 | **High** | Totalmente aislada, prioridad máxima |

---

## 🔒 5. Seguridad y Operación

- DHCP → Desactivado (IP estática del switch).
- Loop Detection → Activado.
- Administración accesible vía:  
  `http://192.168.0.50`

