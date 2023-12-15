# Smokeping Dark Mode Theme

![Smokeping Logo](https://oss.oetiker.ch/smokeping/inc/smokeping-logo.png)

## Beschreibung

Dieses Projekt bietet ein Darkmode-Theme für Smokeping, eine Open-Source-Netzwerküberwachungssoftware. Der Darkmode bietet eine augenfreundliche Benutzeroberfläche für den nächtlichen Einsatz oder für Benutzer, die eine Vorliebe für dunklere Designs haben.

## Vorschau

Hier ist ein Screenshot des Dunkelmodus in Aktion:

![Dunkelmodus Screenshot](https://media.m-s.moe/uploads/MaximilianGT500/20bcc3fe-0b42-4807-bc65-1b8b8da246e4.png)

## Installation
### Neue Installation

<details>
<summary><em>Erweitern, wenn du SmokePing komplett neu installieren möchtest.</em></summary>
<br>
  
1. [Docker](https://docs.docker.com/get-docker/) & Docker Compose Installieren

   Debian (Debian Bookworm 12 (stable), Debian Bullseye 11 (oldstable)):

   ```bash
    sudo apt-get update
    sudo apt-get --assume-yes install ca-certificates curl gnupg
    sudo install -m 0755 -d /etc/apt/keyrings
    curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
    sudo chmod a+r /etc/apt/keyrings/docker.gpg
    echo \
    "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
    "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
    sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    sudo apt-get update
    sudo apt-get --assume-yes install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
   ```

   Ubuntu (Ubuntu Lunar 23.04, Ubuntu Kinetic 22.10, Ubuntu Jammy 22.04 (LTS), Ubuntu Focal 20.04 (LTS)):

   ```bash
    sudo apt-get update
    sudo apt-get --assume-yes install ca-certificates curl gnupg
    sudo install -m 0755 -d /etc/apt/keyrings
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
    sudo chmod a+r /etc/apt/keyrings/docker.gpg
    echo \
    "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
    "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
    sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
    sudo apt-get update
    sudo apt-get --assume-yes install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
   ```
2. Erstelle ein Verzeichnis und Navigiere hinein:
   ```bash
    mkdir /home/smokeping
    cd /home/smokeping
    ```
3. Installiere [Git](https://git-scm.com/) und kopiere das Repository in den selben Ordner.
   ```bash
   apt install git
   git clone https://github.com/maxsrl/SmokePing-Dark.git .
   ```
4. Bearbeite die "[basepage.html](https://github.com/maxsrl/SmokePing-Dark/blob/main/basepage.html)"-Seite. Ich nutze nur einen Placeholder: "XYZExample" die Bilder haben den Prefix: "https://max.srl/assets/images".
   ```bash
   nano basepage.html
   ```
5. Starte nun die Anwendung und viel Spaß!
   ```bash
   docker compose up -d
   ```
Du kannst nun in dein Browser Smomkeping öffnen unter http://deineip/smokeping
</details>

### Bestehende Installation

<details>
<summary><em>Erweitern, wenn du SmokePing bereits mit Docker Installiert hast und das Theme installieren möchtest.</em></summary>
<br>

1. Gehe in das Verzeichnis, wo deine bestehende "docker-compose.yml" ist.
   ```bash
   cd /xyz/xyz
   ```
2. Öffne die "docker-compose.yml"-Datei in deinem Editor wie z.B. [Nano](https://www.nano-editor.org/).
   ```bash
   nano docker-compose.yml
   ```
3. Füge unter "volumes:" diese Zeile hinzu: [Link zur Zeile](https://github.com/maxsrl/SmokePing-Dark/blob/main/docker-compose.yml#L13)
   ```yml
      - /root/smokeping/basepage.html:/etc/smokeping/basepage.html # Dies ist für das Custom Design.
   ```
4. Lade dir die HTML Seite herunter mit z.B. [wGET](https://www.gnu.org/software/wget/) oder [cURL](https://curl.se/)
5. Bearbeite die "[basepage.html](https://github.com/maxsrl/SmokePing-Dark/blob/main/basepage.html)"-Seite. Ich nutze nur einen Placeholder: "XYZExample" die Bilder haben den Prefix: "https://max.srl/assets/images".
   ```bash
   nano basepage.html
   ```
6. Starte nun die Anwendung und viel Spaß!
   ```bash
   docker compose down
   docker compose up -d
   ```
Du kannst nun in dein Browser Smomkeping öffnen unter http://deineip/smokeping
</details>


### Credits

> [SmokePing](https://oss.oetiker.ch/smokeping/index.en.html)
>
> [Docker](https://www.docker.com/)
>
> [LinuxServer](https://docs.linuxserver.io/images/docker-smokeping/)
