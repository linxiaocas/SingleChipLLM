# 🚀 Single-Chip LLM for Embodied AI

> **Run 7 B parameters on a single chip—no cloud, no fans, no problem.**  
> Robotics • Autonomous Driving • Smart Cockpit • Embodied Intelligence

---

## 📌 What’s Inside

| Domain | Demo | Hardware | Latency | Power |
|--------|------|----------|---------|-------|
| Robotic Manipulation | [:movie_camera: 25 s clip](https://github.com/SingleChipLLM/robotics-lm-demo) | STM32MP1 + Coral TPU | **40 ms** | 3.8 W |
| Autonomous Driving | [:movie_camera: 35 s clip](https://github.com/SingleChipLLM/autodrive-lm-demo) | NVIDIA Orin Nano | **120 ms** | 9 W |
| Smart Cockpit | [:movie_camera: 15 s clip](https://github.com/SingleChipLLM/cockpit-lm-demo) | Qualcomm SA8295P | **80 ms** | 5 W |

---

## 🧩 Quick Start

```bash
# 1. Clone the core framework
git clone https://github.com/SingleChipLLM/core.git
cd core

# 2. Fetch a 7 B INT4 model (~1.6 GB → 0.9 GB after quant)
wget https://huggingface.co/SingleChipLLM/MobileLLM-7B-int4

# 3. Build for your target
./scripts/build.sh --target orin-nano --backend tensorrt
```

> 🔍 **First build will take ~5 min**; subsequent incremental builds <20 s.

---

## 📊 Benchmarks (July 2025)

| Model Size | Quant | Chip | Tokens/s | DRAM BW | Power |
|------------|-------|------|----------|---------|-------|
| 7 B        | INT4  | Orin Nano | **15.2** | 42 GB/s | 9.3 W |
| 3 B        | INT8  | STM32MP1 | **8.7**  | 12 GB/s | **3.1 W** |
| 13 B       | INT4  | Orin NX | **9.6**  | 68 GB/s | 15.4 W |

---

## 🧪 Reproduce Our Numbers

```bash
# Run the official benchmark suite
python3 benchmarks/run.py --model 7b-int4 --device orin-nano --scenario single-stream
```

Logs and raw CSV are automatically saved in `results/`.

---

## 🧰 Repositories

| Repo | Description |
|------|-------------|
| [`core`](https://github.com/SingleChipLLM/core) | Inference engine + quant tools |
| [`robotics-lm`](https://github.com/SingleChipLLM/robotics-lm) | ROS 2 nodes for manipulation |
| [`autodrive-lm`](https://github.com/SingleChipLLM/autodrive-lm) | Lane-change planner w/ LLM |
| [`cockpit-lm`](https://github.com/SingleChipLLM/cockpit-lm) | Voice assistant w/ local intent |
| [`datasets`](https://github.com/SingleChipLLM/datasets) | Curated edge-AI corpora |

---

## 🤝 Contributing

We ❤️ pull requests.  
- **Hardware partners**: see [`HARDWARE.md`](docs/HARDWARE.md) for porting guide.  
- **Model hackers**: open an issue with the tag `compression-techniques`.  
- **Robot builders**: share your videos in [`Discussions`](https://github.com/SingleChipLLM/core/discussions).

---

## 📜 Citation

If you use this work, please cite:

```bibtex
@misc{singlechip2025,
  title={Single-Chip LLM: Sub-10 W Inference for Embodied AI},
  author={SingleChipLLM Team},
  year={2025},
  url={https://github.com/linxiaocas/SingleChipLLM/core}
}
```

---

## 📄 License

Apache 2.0 – see [LICENSE](LICENSE).  
Trademarks belong to their respective owners.

---

<div align="center">

![Header](./single-chip-llm.svg)

</div>
