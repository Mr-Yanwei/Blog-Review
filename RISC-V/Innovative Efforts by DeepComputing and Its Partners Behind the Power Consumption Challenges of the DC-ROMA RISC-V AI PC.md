# Innovative Efforts by DeepComputing and Its Partners Behind the Power Consumption Challenges of the DC-ROMA RISC-V AI PC

The EIC7702x used in the DC-ROMA RISC-V AI PC is the world’s first RISC-V SoC chiplet designed for the low-power domain, representing a major architectural innovation by the ESWIN and DeepComputing teams in both RISC-V silicon and product applications. The chip adopts a brand-new die-to-die design. 
However, to maintain a stable die-to-die connection, approximately 5W of power is required, and this consumption cannot be further reduced without risking link instability or disconnection. Despite this limitation, the chip remains a high-performance solution within the RISC-V ecosystem. Below is an objective discussion of this processor.

## A Landmark Technological Milestone
1. The World’s First 40 TOPS RISC-V AI PC
DC-ROMA AI PC is powered by the EIC7702X processor, which features a dual-die interconnect design. Using a pioneering die-to-die packaging technology, it integrates two 64-bit RISC-V chips, delivering a peak AI performance of up to 50 TOPS (with 40 TOPS contributed by the NPU alone). This marks a significant breakthrough for the RISC-V architecture in high-performance computing.
2. A Revolutionary Application of Modular Design
Built on Framework’s modular architecture, the device can flexibly switch between laptop and desktop form factors while remaining compatible with the Framework ecosystem. This design significantly reduces hardware adaptation costs for developers and provides a solid physical foundation for software optimization within the RISC-V ecosystem.
## Objective Analysis of Power Consumption
1. Balancing Performance and Power Efficiency
- Sources of power consumption: The die-to-die interconnect and multi-core high-frequency design (2 GHz clock speed) require higher power delivery. This is the necessary trade-off for enabling capabilities such as 8K video encoding and on-device AI inference.
- Horizontal comparison: Compared with x86 solutions offering similar compute capability (for example, Intel Lunar Lake with a 48 TOPS NPU consuming approximately 30W), DC-ROMA achieves comparable performance under an open architecture, with its energy-efficiency optimization still within a reasonable and improvable range.
2. Ongoing Progress in Power Optimization
- Hardware level: Next-generation RISC-V chips already integrate customized AI instruction sets, reducing redundant computation through vector acceleration.
- Software collaboration: Ubuntu 24.04 LTS includes deep optimizations for the RISC-V instruction set, and further reductions in idle power consumption are expected through future kernel scheduling improvements.
## Core Focus on Technical Value
1. Breakthrough Significance Over Short-Term Limitations
As the world’s first commercially available RISC-V AI PC, its core value lies in validating the feasibility of using an open architecture to support edge AI computing. Power consumption challenges are a common bottleneck in technological iteration, rather than a flaw inherent to the architecture itself.
2. Hardware Sustainability
DC-ROMA’s modular design allows users to upgrade hardware by replacing the mainboard alone. Future low-power chips can be adopted seamlessly, fundamentally avoiding the energy inefficiencies caused by “hardware lock-in.”
## Conclusion
In summary, the higher power consumption of the DC-ROMA RISC-V AI PC is the price that must be paid to achieve high performance. The DeepComputing team has already made every possible effort to optimize power efficiency and will continue to do so. Elevating RISC-V from small-scale IoT scenarios to the high-performance AI PC arena is a remarkable achievement. With future process node advancements and instruction-set extensions, the performance-per-watt ratio will only continue to improve.
