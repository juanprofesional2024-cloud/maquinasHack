# 🛡️ Writeup: Máquina Debian DNS-Topo (The Hackers Labs)

Un informe detallado sobre la enumeración, explotación y escalada de privilegios de la máquina.

---

## 📊 Ficha Técnica
* **OS:** Linux (Debian)
* **Dificultad:** Fácil / Media
* **Plataforma:** The Hackers Labs
* **IP de la Víctima:** `10.10.X.X`

---

## 🔎 1. Enumeración y Reconocimiento

### Escaneo de Puertos (Nmap)
Comenzamos con un escaneo agresivo para identificar servicios e índices abiertos en la máquina objetivo:

```bash
nmap -p- -sV -sC -Pn --min-rate 5000 10.10.X.X -oN nmap_scan.txt
```

Aquí se muestran los puertos abiertos encontrados (ej. SSH, DNS, HTTP):

![Escaneo de Nmap](../.images/nmap-scan.png)

---

## 🚀 2. Explotación (Acceso Inicial)

### Análisis del Servicio DNS / Web
[Explica brevemente qué vulnerabilidad encontraste o qué configuración incorrecta explotaste].

Ejecutamos el siguiente payload o comando para obtener una Reverse Shell:

![Ejecución del Exploit](../.images/exploit-proof.png)

---

## ⚡ 3. Escalada de Privilegios

Una vez dentro como usuario de bajos privilegios, revisamos los vectores de escalada (SUDO, SUID, Tareas Cron, etc.).

### Obtención de Root
[Explica cómo pasaste de usuario normal a Root].

¡Finalmente logramos comprometer el sistema por completo y obtener la flag de root!

![Flag de Root](../.images/root-flag.png)

---

## 💡 Lecciones Aprendidas
1. Mantener las zonas DNS protegidas para evitar transferencias de zona no autorizadas.
2. No dejar credenciales por defecto o scripts vulnerables expuestos en servidores web.

