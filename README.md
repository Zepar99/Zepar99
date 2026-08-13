<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0D1117,100:0077B6&height=200&section=header&text=PRATIK%20BORSE&fontSize=56&fontColor=00B4D8&fontAlignY=36&animation=fadeIn&desc=Low-Latency%20Systems%20Built%20From%20Scratch&descAlignY=58&descSize=18" alt="Pratik Borse" width="100%"/>

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=20&pause=1000&color=00B4D8&center=true&vCenter=true&width=650&lines=Systems+Programmer+%7C+C%2B%2B;Building+low-latency%2C+networked+systems+from+scratch;40K%2B+orders%2Fsec+%7C+sub-2ms+p99+latency;Real-Time+Digital+Twin+Engineer+by+day" alt="Typing SVG"/>

<br/>

<img src="https://img.shields.io/badge/matching--engine--cpp-40K%2B_orders%2Fsec-00B4D8?style=for-the-badge&labelColor=0d1117"/>
<img src="https://img.shields.io/badge/p99_latency-%3C2ms_@100_clients-0077B6?style=for-the-badge&labelColor=0d1117"/>
<img src="https://img.shields.io/badge/redis--clone--cpp-RESP_%2B_epoll_%2B_AOF%2FRDB-48CAE4?style=for-the-badge&labelColor=0d1117"/>
<img src="https://img.shields.io/badge/orders--processed-2M%2B_sustained-00B4D8?style=for-the-badge&labelColor=0d1117"/>

</div>

<div align="center">
<br/>
<i>"I'd rather understand how a system performs under load than assume it — so I built a Redis-style store and a matching engine myself, then benchmarked both. That's the whole pitch.</i>
<br/><br/>
</div>

---

```text
$ who-am-i

Pratik Borse — Systems Programmer (C++)
Real-Time Simulation Engineer · Pune, India


$ cat mission.txt

By day:
  Real-time Digital Twin simulations for CNC & robotic systems.

By night:
  Event loops. Wire protocols. Matching engines.
  Built from scratch because understanding the abstraction
  is more interesting than simply using it.


$ ls core/

redis-clone-cpp/
             └─ epoll reactor · RESP · AOF/RDB persistence

matching-engine-cpp/
             └─ price-time priority · 40K+ orders/sec · sub-2ms p99
```

---

## 🧪 Benchmarked, Not Assumed

Two systems. Built from the socket layer up. Proven under a load harness I wrote myself — because "should be fast" isn't a metric.

### ⚙️ matching-engine-cpp
*A low-latency limit order matching engine — price-time priority, proven under real concurrent load.*

- FIFO matching with partial fills, **O(1) order cancellation** via an auxiliary index
- A custom multi-threaded **TCP load-test harness** — real throughput and p50/p95/p99 latency, not guesses

**Sub-2ms p99 latency** at 100 concurrent clients, holding steady past **2,000,000** total orders processed.

| Concurrent Clients | Throughput |
|:---:|:---:|
| 10 | 40,739 orders/sec |
| 100 | **50,093 orders/sec** (peak) |
| 1,000 | 46,768 orders/sec |

```mermaid
flowchart LR
    O[Incoming Order] --> T{Limit or Market?}
    T -->|Limit| B[Order Book]
    T -->|Market| M[Match Immediately]
    B --> P[Price-Time Priority Queue]
    P --> F{Crossable?}
    F -->|Yes| X["Execute Trade<br/>(partial fills supported)"]
    F -->|No| R[Rest on Book]
    M --> X
    X --> C["O(1) Cancel-Index Update"]
    R --> C
    C --> A[Ack / Fill to Client]
```

**[→ github.com/Zepar99/matching-engine-cpp](https://github.com/Zepar99/matching-engine-cpp)**

<br/>

### 🗄️ redis-clone-cpp
*A Redis-style in-memory key-value store, built from raw sockets up.*

- Single-threaded **epoll** reactor — concurrent TCP clients, zero locks on the data store
- A real **RESP wire protocol** — multibulk parsing with partial-read handling, plus inline fallback
- **AOF + RDB** persistence, selectable at runtime (`--persistence=aof|rdb|both`)
- TTL/expiry via lazy deletion, with structured timestamped logging

```mermaid
flowchart TD
    L[epoll_wait] --> N{Event Type}
    N -->|New connection| ACC[Accept + Register FD]
    N -->|Socket readable| R[Read Into Buffer]
    R --> PARSE["Parse RESP<br/>(multibulk + inline fallback)"]
    PARSE --> COMPLETE{Full Command?}
    COMPLETE -->|No, more to read| L
    COMPLETE -->|Yes| EXEC[Execute Command]
    EXEC --> WRITE[Write Response to Socket]
    WRITE --> PERSIST[AOF / RDB Write]
    PERSIST --> L
    ACC --> L
```

**[→ github.com/Zepar99/redis-clone-cpp](https://github.com/Zepar99/redis-clone-cpp)**

---

<details>
<summary><b>🕹️ Before the Backend: Game Dev Era</b></summary>
<br/>

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

</details>

---

## 🧰 Toolchain

<p align="center">
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

## 📈 GitHub Activity

<table>
<tr>
<td width="60%">

<img src="https://github-readme-stats.vercel.app/api?username=Zepar99&show_icons=true&hide_border=true&bg_color=0D1117&title_color=00B4D8&icon_color=48CAE4&text_color=C9D1D9" alt="GitHub Stats" width="100%"/>

</td>
<td width="40%">

<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Zepar99&layout=compact&hide_border=true&bg_color=0D1117&title_color=00B4D8&text_color=C9D1D9" alt="Top Languages" width="100%"/>

</td>
</tr>
</table>

<p align="center">
<img src="https://streak-stats.demolab.com?user=Zepar99&hide_border=true&background=0D1117&ring=00B4D8&fire=0077B6&currStreakNum=48CAE4&sideNums=48CAE4&currStreakLabel=00B4D8&sideLabels=8B949E&dates=8B949E" alt="GitHub Streak"/>
</p>

---

## 🛠️ Currently Compiling

```bash
$ cat currently_focused_on.txt
├── DSA fluency — interview-speed pattern recognition
├── Multi-threaded concurrency patterns
├── Memory-safety tooling (sanitizers, testing)
└── Low-latency system design
```

---

<div align="center">

## 📡 Open a Connection

Always up for talking systems, latency budgets, or why your p99 looks like that.

<a href="mailto:pratikkborse@gmail.com"><img src="https://img.shields.io/badge/Gmail-pratikkborse%40gmail.com-00B4D8?style=for-the-badge&logo=gmail&logoColor=white&labelColor=0d1117" alt="Email"/></a>
<a href="https://www.linkedin.com/in/pratik-borse"><img src="https://img.shields.io/badge/LinkedIn-pratik--borse-0077B6?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0d1117" alt="LinkedIn"/></a>
<a href="https://github.com/Zepar99"><img src="https://img.shields.io/badge/GitHub-Zepar99-48CAE4?style=for-the-badge&logo=github&logoColor=white&labelColor=0d1117" alt="GitHub"/></a>

<br/><br/>

<img src="https://komarev.com/ghpvc/?username=Zepar99&label=Profile%20Views&color=00b4d8&style=for-the-badge" alt="Profile Views"/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0077B6,100:0D1117&height=120&section=footer&text=Thanks%20for%20reading&fontSize=16&fontColor=48CAE4&fontAlignY=75&animation=fadeIn" alt="footer" width="100%"/>

</div>
