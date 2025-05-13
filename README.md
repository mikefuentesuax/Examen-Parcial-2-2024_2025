#Examen-Parcial-2-2024_2025
https://github.com/mikefuentesuax/Examen-Parcial-2-2024_2025.git

# Parte I – Misiones de Conocimiento Teórico

## Misión 1: Reconexión en la Base Eco (Hoth) – Direccionamiento IP y Subredes

**Red Base:** 172.16.0.0/24

* **Comando Central:** ~50 hosts
* **Defensa Perimetral:** ~30 hosts
* **Centro Médico:** ~20 hosts
* **Hangar y Taller:** ~14 hosts
* **Enlace Troncal:** Necesita una subred para este enlace.

**Asignación de Subredes:**

| Departamento          | Dirección de Red | Máscara de Subred (/xx) | Hosts Útiles | Rango de Hosts         |
| :-------------------- | :--------------- | :--------------------- | :----------- | :--------------------- |
| Comando Central       | 172.16.0.0       | /26                   | 62           | 172.16.0.1 - 172.16.0.62  |
| Defensa Perimetral    | 172.16.0.64      | /27                   | 30           | 172.16.0.65 - 172.16.0.94  |
| Centro Médico         | 172.16.0.96      | /27                   | 30           | 172.16.0.97 - 172.16.0.126 |
| Hangar y Taller       | 172.16.0.128     | /28                   | 14           | 172.16.0.129 - 172.16.0.142 |
| Enlace Troncal        | 172.16.0.144     | /30                   | 2            | 172.16.0.145 - 172.16.0.146 |

