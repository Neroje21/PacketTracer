# LAN síť – Cisco Packet Tracer

## Popis úlohy

Byla vytvořena jednoduchá LAN síť obsahující dva switche, dva počítače a dva servery. Síť slouží k demonstraci základních síťových služeb – DHCP, DNS a WEB.

---

## Výpočet X

Hodnota X byla vypočítána podle zadání:

Součet ordinálních hodnot písmen příjmení (velkými bez diakritiky) modulo 256:

**X = 207**

---

## Adresace sítě

Použitý rozsah:

**192.168.207.0 /24**

| Zařízení | IP adresa      | Poznámka        |
| -------- | -------------- | --------------- |
| SRV1     | 192.168.207.2  | DHCP + DNS      |
| SRV2     | 192.168.207.3  | WEB             |
| PC1      | DHCP           | dynamicky       |
| PC2      | DHCP           | dynamicky       |
| Gateway  | 192.168.207.1  |                 |

Maska: **255.255.255.0**

---

## Topologie sítě

* PC1 a PC2 jsou připojeny ke switchi S1
* Switch S1 je propojen se S2
* SRV1 a SRV2 jsou připojeny ke switchi S2
* Laptop slouží pro konfiguraci switchů přes terminál

---

## Konfigurace zařízení

### SRV1 (DHCP + DNS)

* Nastavena statická IP: **192.168.207.2**
* Zapnuté služby:

  * DHCP:

    * Pool: LAN
    * Start IP: 192.168.207.100
    * Gateway: 192.168.207.1
    * DNS: 192.168.207.2
  * DNS:

    * Doména: **solnar.cz**
    * Záznam:

      * solnar.cz → 192.168.207.3

---

### SRV2 (WEB)

* IP: **192.168.207.3**
* Zapnutá služba HTTP
* Webová stránka obsahuje:

  * jméno a příjmení autora

---

### PC1

* Nastaveno na DHCP
* Automaticky získává:

  * IP adresu
  * masku
  * gateway
  * DNS

---

### PC2

* Nastaveno na DHCP
* Automaticky získává:

  * IP adresu
  * masku
  * gateway
  * DNS

---

## Testování

### IP konfigurace (PC1 a PC2)

Příkaz:

```
ipconfig
```

---

### Ping na web server

Testováno z PC1:

* přes IP:

```
ping 192.168.207.3
```

* přes doménu:

```
ping solnar.cz
```

---

### Webový přístup

V prohlížeči:

* http://192.168.207.3
* http://solnar.cz

---

## Screenshoty

* <img width="563" height="304" alt="Snímek obrazovky 2026-04-10 135053" src="https://github.com/user-attachments/assets/19178a05-0dad-4a8f-a0d4-bb9566c704aa" />
* Laptop – konfigurace switchů
* <img width="709" height="718" alt="Snímek obrazovky 2026-04-10 134815" src="https://github.com/user-attachments/assets/1406e23e-e760-42a0-b549-78f258e6d45c" />
* <img width="700" height="715" alt="Snímek obrazovky 2026-04-10 134927" src="https://github.com/user-attachments/assets/ba82e984-0934-4841-8a52-cdcbe6e775e0" />
* PC1 – ipconfig
* <img width="708" height="715" alt="Snímek obrazovky 2026-04-10 133919" src="https://github.com/user-attachments/assets/9481ddf1-4da8-442e-9b0d-7cdab7e40aad" />
* PC1 – ping (IP + DNS)
* <img width="714" height="722" alt="Snímek obrazovky 2026-04-10 134105" src="https://github.com/user-attachments/assets/fa3af9f8-9df7-4f32-b1a1-e973c4da1c8b" />
* Nastavení DHCP
* <img width="502" height="395" alt="Snímek obrazovky 2026-04-10 134204" src="https://github.com/user-attachments/assets/07d41149-cdcf-4efb-9704-854819bb67a8" />
* Nastavení DNS
* <img width="522" height="253" alt="Snímek obrazovky 2026-04-10 134226" src="https://github.com/user-attachments/assets/814f5096-a26c-4176-9562-05a0d17817b2" />
* Nastavení SRV1
* <img width="506" height="383" alt="Snímek obrazovky 2026-04-10 134312" src="https://github.com/user-attachments/assets/b42d78ff-dbb7-4775-b63f-b60e29126d2f" />
* Nastavení SRV2
* <img width="496" height="372" alt="Snímek obrazovky 2026-04-10 134301" src="https://github.com/user-attachments/assets/4ca517d8-a697-4bd4-ad22-5eeb837b7eb6" />
* <img width="513" height="300" alt="Snímek obrazovky 2026-04-10 134251" src="https://github.com/user-attachments/assets/6a9a56c1-a7a2-4232-befc-b665b9063862" />


---

## Soubory

* `lan.pkt` – síť v Cisco Packet Traceru
* `README.md` – dokumentace

---
