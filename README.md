# IoT MQTT Chat App

> Lightweight IoT chat application — Python + **MQTT** (paho-mqtt) + **Tkinter** GUI. Demonstrates real-time publish/subscribe messaging with a desktop client plus simple CLI publisher/subscriber examples.

[![Python](https://img.shields.io/badge/Python-3.7%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![MQTT](https://img.shields.io/badge/MQTT-660066?style=flat-square&logo=mqtt&logoColor=white)](https://mqtt.org/)
[![Tkinter](https://img.shields.io/badge/Tkinter-GUI-FFC107?style=flat-square)](https://docs.python.org/3/library/tkinter.html)
[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

Built as part of Semester 6B IoT Lab — University of Moratuwa.

---

## What's in the box

- **GUI chat client** (`Chat_App_Lab.py`) — connect with a name + topic, real-time MQTT chat, scrollable history. Type `exit` to quit.
- **CLI publisher** (`publisher.py`) — emits a test message every 5s to `/system`.
- **CLI subscriber** (`subscriber.py`) — listens on `/system` and prints incoming messages.

## Run it

```bash
git clone https://github.com/Anjanamb/IoT-MQTT-ChatApp.git
cd IoT-MQTT-ChatApp
pip install paho-mqtt
```

### GUI chat client

```bash
python Chat_App_Lab.py
```

Enter a name + topic, click **Connect**. Everyone on the same topic sees messages in real time.

### CLI publisher / subscriber

```bash
python publisher.py     # emits every 5 seconds
python subscriber.py    # listens
```

## How it works

- **Broker:** HiveMQ's public broker (`broker.hivemq.com:1883`) by default
- **Wire format:** JSON

```json
{ "Name": "Alice", "msg": "Hello world!" }
```

The GUI client combines publisher and subscriber logic with a Tkinter window.

## Roadmap

- [ ] Private messaging and multi-topic chatrooms
- [ ] Message timestamps
- [ ] TLS / SSL encryption
- [ ] Packaged desktop executable (PyInstaller)
- [ ] Web-based MQTT chat

## License

[MIT](LICENSE) — see [anjanamb.github.io](https://anjanamb.github.io/) for more projects.
