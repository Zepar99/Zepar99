<h1 align="center">Pratik Borse</h1>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=20&pause=1000&color=00B4D8&center=true&vCenter=true&width=650&lines=Systems+Programmer+%7C+C%2B%2B;Building+low-latency%2C+networked+systems+from+scratch;40K%2B+orders%2Fsec+%7C+sub-2ms+p99+latency;Real-Time+Digital+Twin+Engineer+by+day" alt="Typing SVG" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/matching--engine--cpp-40K%2B_orders%2Fsec-00B4D8?style=for-the-badge&labelColor=0d1117"/>
  <img src="https://img.shields.io/badge/p99_latency-%3C2ms_@100_clients-0077B6?style=for-the-badge&labelColor=0d1117"/>
  <img src="https://img.shields.io/badge/redis--clone--cpp-RESP_%2B_epoll_%2B_AOF%2FRDB-48CAE4?style=for-the-badge&labelColor=0d1117"/>
</p>

---

```bash
$ whoami
Pratik Borse — Systems Programmer (C++) | Real-Time Simulation Engineer, Pune, India

$ cat focus.txt
Building networked, concurrent, low-latency systems from scratch in C++.
Day job: real-time Digital Twin simulations for CNC & robotic systems.

$ ls -la projects/featured/
drwxr-xr-x  redis-clone-cpp/       # epoll event loop, RESP protocol, AOF+RDB persistence
drwxr-xr-x  matching-engine-cpp/   # price-time priority matching, 40K+ orders/sec benchmarked
```

---

## ⚡ Featured Builds

### redis-clone-cpp
> A Redis-style in-memory key-value store, built from raw sockets up.

- Single-threaded **epoll** reactor — concurrent TCP clients, zero locks on the data store
- Real **RESP wire protocol** — multibulk parsing with partial-read handling, plus inline fallback
- **AOF + RDB** persistence, selectable at runtime (`--persistence=aof|rdb|both`)
- TTL/expiry (lazy deletion), structured timestamped logging

**[→ github.com/Zepar99/redis-clone-cpp](https://github.com/Zepar99/redis-clone-cpp)**

### matching-engine-cpp
> A low-latency limit order matching engine — price-time priority, benchmarked under real load.

- FIFO matching with partial fills, **O(1) order cancellation** via an auxiliary index
- Custom multi-threaded **TCP load-test harness** — real throughput + p50/p95/p99 latency, not guesses
- `40,739 → 50,093 → 46,768` orders/sec sustained across `10 → 100 → 1,000` concurrent clients
- Sub-2ms p99 latency at 100 concurrent clients; held steady past 2M total orders

**[→ github.com/Zepar99/matching-engine-cpp](https://github.com/Zepar99/matching-engine-cpp)**

---

## 🎮 Also Built (game dev background)

<table>
<tr>
<td width="50%">

**[The Dungeon Tale](https://github.com/Zepar99/The-Dungeon-Tale)**
Dungeon puzzle game — two players, one controller. Unity + C#.

**[Battle Tanks](https://github.com/Zepar99/Battle-Tank)**
3D tank combat. Unity + C#.

</td>
<td width="50%">

**[Duet Game](https://github.com/Zepar99/Duet-Game)** · 2D hyper-casual
**[Hill Climb](https://github.com/Zepar99/Hill-Climb)** · Physics racer
**[Paper Plane](https://github.com/Zepar99/Paper-Plane)** · 2D survival
**[The Explorer](https://github.com/Zepar99/The-Explorer)** · 2D platformer

</td>
</tr>
</table>

---

## 🛠️ Stack

<p>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/cplusplus/cplusplus-original.svg" width="42" height="42" alt="C++"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/csharp/csharp-original.svg" width="42" height="42" alt="C#"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" width="42" height="42" alt="Python"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" width="42" height="42" alt="TypeScript"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" width="42" height="42" alt="Linux"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/windows8/windows8-original.svg" width="42" height="42" alt="Windows"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/unity/unity-original.svg" width="42" height="42" alt="Unity"/>
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original.svg" width="42" height="42" alt="Git"/>
</p>

---

```bash
$ cat currently_focused_on.txt
├── DSA fluency — interview-speed pattern recognition
├── Multi-threaded concurrency patterns
├── Memory-safety tooling (sanitizers, testing)
└── Low-latency system design
```

<p align="center">
📫 <a href="mailto:pratikkborse@gmail.com">pratikkborse@gmail.com</a> · <a href="https://www.linkedin.com/in/pratik-borse">LinkedIn</a>
</p>
