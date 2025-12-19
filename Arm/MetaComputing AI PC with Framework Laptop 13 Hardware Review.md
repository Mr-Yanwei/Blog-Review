# MetaComputing AI PC with Framework Laptop 13 Hardware Review
**Test Environment:**
- System: Debian GNU/Linux 12.11 (bookworm) aarch64
- Kernel: Linux 6.6.89
- Test Conditions: Fresh system boot, no background loads (results reflect theoretical performance peaks). Real-world usage varies due to thermal/power management.


## Basic Information
- MC AI PC: https://metacomputing.io/collections/frontpage/products/metacomputing-aipc

## System Information
```
roma@debian ~> fastfetch
        _,met$$$$$gg.          roma@debian
     ,g$$$$$$$$$$$$$$$P.       -----------
   ,g$$P""       """Y$$.".     OS: Debian GNU/Linux 12.11 (bookworm) aarch64
  ,$$P'              `$$$.     Host: MC FML13V04 Board (1.0)
',$$P       ,ggs.     `$$b:    Kernel: Linux 6.6.89-cix-build-generic
`d$$'     ,$P"'   .    $$$     Uptime: 11 mins
 $$P      d$'     ,    $$P     Packages: 2632 (dpkg)
 $$:      $$.   -    ,d$$'     Shell: fish 3.6.0
 $$;      Y$b._   _,d$P'       Display (BOE095F): 2256x1504 @ 2x in 13", 60 Hz [Built-in]
 Y$$.    `.`"Y$$$$P"'          DE: GNOME 43.9
 `$$b      "-.__               WM: Mutter (Wayland)
  `Y$$b                        WM Theme: Adwaita
   `Y$$.                       Theme: Adwaita [GTK2/3/4]
     `$$b.                     Icons: Adwaita [GTK2/3/4]
       `Y$$b.                  Font: Cantarell (11pt) [GTK2/3/4]
         `"Y$b._               Cursor: Adwaita (24px)
             `""""             Terminal: /dev/pts/0
                               CPU: Cortex-A720*2 + Cortex-A520*4 + Cortex-A720*6 (12) @ 2.60 GHz
                               GPU: Mali-G720-Immortalis [Integrated]
                               Memory: 7.74 GiB / 30.94 GiB (25%)
                               Swap: 0 B / 976.00 MiB (0%)
                               Disk (/): 21.29 GiB / 466.95 GiB (5%) - ext4
                               Local IP (wlan0): 192.168.50.38/24
                               Battery (ABC): 95% [AC Connected]
                               Locale: en_US.UTF-8
```
<img width="1280" height="853" alt="image" src="https://github.com/user-attachments/assets/491fff37-7c7b-40cd-b886-1b8c80d44ece" />


## CPU 
- **Geekbench 6**
<img width="1280" height="636" alt="image" src="https://github.com/user-attachments/assets/1ab29ad2-5127-410c-a03f-b3769e7fad02" />

- **Geekbench 6 Comparison Chart（Part of the data is sourced from the internet）**
<img width="1089" height="589" alt="image" src="https://github.com/user-attachments/assets/cd0e4a94-bf94-4c1e-afc1-7a24e1591023" />



- **Coremark**：Strong single-core performance (exceeds embedded ARM) and linear multi-core scaling.
  - **Single-Core**：24832.38 Iterations/Sec
```
roma@debian ~/coremark (main)> make compile XCFLAGS="-DMULTITHREAD=1 -DUSE_PTHREAD"
roma@debian ~/coremark (main)> ./coremark.exe
2K performance run parameters for coremark.
CoreMark Size    : 666
Total ticks      : 12081
Total time (secs): 12.081000
Iterations/Sec   : 24832.381425
Iterations       : 300000
Compiler version : GCC12.2.0
Compiler flags   : -O2 -DMULTITHREAD=1 -DUSE_PTHREAD  -lrt -lpthread
Memory location  : Please put data memory location here
                        (e.g. code in flash, data on heap etc)
seedcrc          : 0xe9f5
[0]crclist       : 0xe714
[0]crcmatrix     : 0x1fd7
[0]crcstate      : 0x8e3a
[0]crcfinal      : 0xcc42
Correct operation validated. See README.md for run and reporting rules.
CoreMark 1.0 : 24832.381425 / GCC12.2.0 -O2 -DMULTITHREAD=1 -DUSE_PTHREAD  -lrt -lpthread / Heap
```
- 
  - **Multi-Core (64 threads)**：186003.26 Iterations/Sec 
```
roma@debian ~/coremark (main)> make compile XCFLAGS="-DMULTITHREAD=64 -DUSE_PTHREAD"
roma@debian ~/coremark (main)> ./coremark.exe
2K performance run parameters for coremark.
CoreMark Size    : 666
Total ticks      : 103224
Total time (secs): 103.224000
Iterations/Sec   : 186003.255057
Iterations       : 19200000
Compiler version : GCC12.2.0
Compiler flags   : -O2 -DMULTITHREAD=64 -DUSE_PTHREAD  -lrt -lpthread
Parallel PThreads : 64
Memory location  : Please put data memory location here
                        (e.g. code in flash, data on heap etc)
seedcrc          : 0xe9f5

Correct operation validated. See README.md for run and reporting rules.
CoreMark 1.0 : 186003.255057 / GCC12.2.0 -O2 -DMULTITHREAD=64 -DUSE_PTHREAD  -lrt -lpthread / Heap / 64:PThreads
```

## GPU Performance (Mali-G720-Immortalis)
- **Glmark2 Score**: 3845 (800×600 windowed)
- **Peak FPS**: ~5000 (e.g., texture-filter=mipmap: 4890 FPS).
```
=======================================================
    glmark2 2023.01
=======================================================
    OpenGL Information
    GL_VENDOR:      ARM
    GL_RENDERER:    Mali-G720-Immortalis
    GL_VERSION:     OpenGL ES 3.2 v1.r53p0-00eac0.51e7b43a8ca32d45d7e15e03e4ee52d8
    Surface Config: buf=32 r=8 g=8 b=8 a=8 depth=24 stencil=0 samples=0
    Surface Size:   800x600 windowed
=======================================================
[build] use-vbo=false: FPS: 4030 FrameTime: 0.248 ms
[build] use-vbo=true: FPS: 4731 FrameTime: 0.211 ms
[texture] texture-filter=nearest: FPS: 4857 FrameTime: 0.206 ms
[texture] texture-filter=linear: FPS: 4790 FrameTime: 0.209 ms
[texture] texture-filter=mipmap: FPS: 4890 FrameTime: 0.205 ms
[shading] shading=gouraud: FPS: 4573 FrameTime: 0.219 ms
[shading] shading=blinn-phong-inf: FPS: 4647 FrameTime: 0.215 ms
[shading] shading=phong: FPS: 4550 FrameTime: 0.220 ms
[shading] shading=cel: FPS: 4317 FrameTime: 0.232 ms
[bump] bump-render=high-poly: FPS: 3131 FrameTime: 0.319 ms
[bump] bump-render=normals: FPS: 4795 FrameTime: 0.209 ms
[bump] bump-render=height: FPS: 5018 FrameTime: 0.199 ms
[effect2d] kernel=0,1,0;1,-4,1;0,1,0;: FPS: 4620 FrameTime: 0.216 ms
[effect2d] kernel=1,1,1,1,1;1,1,1,1,1;1,1,1,1,1;: FPS: 4243 FrameTime: 0.236 ms
[pulsar] light=false:quads=5:texture=false: FPS: 4899 FrameTime: 0.204 ms
[desktop] blur-radius=5:effect=blur:passes=1:separable=true:windows=4: FPS: 2905 FrameTime: 0.344 ms
[desktop] effect=shadow:windows=4: FPS: 4103 FrameTime: 0.244 ms
[buffer] columns=200:interleave=false:update-dispersion=0.9:update-fraction=0.5:update-method=map: FPS: 580 FrameTime: 1.726 ms
[buffer] columns=200:interleave=false:update-dispersion=0.9:update-fraction=0.5:update-method=subdata: FPS: 564 FrameTime: 1.776 ms
[buffer] columns=200:interleave=true:update-dispersion=0.9:update-fraction=0.5:update-method=map: FPS: 853 FrameTime: 1.172 ms
[ideas] speed=duration: FPS: 2419 FrameTime: 0.414 ms
[jellyfish] <default>: FPS: 4045 FrameTime: 0.247 ms
[terrain] <default>: FPS: 653 FrameTime: 1.532 ms
[shadow] <default>: FPS: 4284 FrameTime: 0.233 ms
[refract] <default>: FPS: 1340 FrameTime: 0.747 ms
[conditionals] fragment-steps=0:vertex-steps=0: FPS: 4608 FrameTime: 0.217 ms
[conditionals] fragment-steps=5:vertex-steps=0: FPS: 4574 FrameTime: 0.219 ms
[conditionals] fragment-steps=0:vertex-steps=5: FPS: 4682 FrameTime: 0.214 ms
[function] fragment-complexity=low:fragment-steps=5: FPS: 4641 FrameTime: 0.215 ms
[function] fragment-complexity=medium:fragment-steps=5: FPS: 4801 FrameTime: 0.208 ms
[loop] fragment-loop=false:fragment-steps=5:vertex-steps=5: FPS: 4500 FrameTime: 0.222 ms
[loop] fragment-steps=5:fragment-uniform=false:vertex-steps=5: FPS: 4808 FrameTime: 0.208 ms
[loop] fragment-steps=5:fragment-uniform=true:vertex-steps=5: FPS: 4491 FrameTime: 0.223 ms
=======================================================
                                  glmark2 Score: 3845 
=======================================================
```

## Memory (32GB LPDDR5)
- **Bandwidth:**
  - Copy: 14–16 GB/s
  - Fill: 35–41 GB/s (e.g., standard memset: 41.25 GB/s).
- **Latency**:
  - 64MB block (single/dual random read):
    - Normal pages: 194.1 ns / 228.1 ns
    - Huge pages: 175.6 ns / 210.6 ns
**Analysis**: High throughput (LPDDR5/X-class) and low latency ensure snappy system responsiveness.
```
tinymembench v0.4.9 (simple benchmark for memory throughput and latency)

==========================================================================
== Memory bandwidth tests                                               ==
==                                                                      ==
== Note 1: 1MB = 1000000 bytes                                          ==
== Note 2: Results for 'copy' tests show how many bytes can be          ==
==         copied per second (adding together read and writen           ==
==         bytes would have provided twice higher numbers)              ==
== Note 3: 2-pass copy means that we are using a small temporary buffer ==
==         to first fetch data into it, and only then write it to the   ==
==         destination (source -> L1 cache, L1 cache -> destination)    ==
== Note 4: If sample standard deviation exceeds 0.1%, it is shown in    ==
==         brackets                                                     ==
==========================================================================

 C copy backwards                                     :  14892.4 MB/s (1.0%)
 C copy backwards (32 byte blocks)                    :  15205.4 MB/s (0.4%)
 C copy backwards (64 byte blocks)                    :  15140.4 MB/s (0.3%)
 C copy                                               :  14994.8 MB/s (0.3%)
 C copy prefetched (32 bytes step)                    :  14132.7 MB/s (0.2%)
 C copy prefetched (64 bytes step)                    :  14301.2 MB/s (0.8%)
 C 2-pass copy                                        :  14294.2 MB/s
 C 2-pass copy prefetched (32 bytes step)             :  13718.6 MB/s
 C 2-pass copy prefetched (64 bytes step)             :  14677.6 MB/s (0.3%)
 C fill                                               :  36013.7 MB/s (2.1%)
 C fill (shuffle within 16 byte blocks)               :  35850.4 MB/s (2.0%)
 C fill (shuffle within 32 byte blocks)               :  35094.1 MB/s (0.5%)
 C fill (shuffle within 64 byte blocks)               :  35493.6 MB/s (0.4%)
 ---
 standard memcpy                                      :  16168.9 MB/s (1.9%)
 standard memset                                      :  41249.7 MB/s (5.9%)
 ---
 NEON LDP/STP copy                                    :  16664.6 MB/s (1.0%)
 NEON LDP/STP copy pldl2strm (32 bytes step)          :  15130.8 MB/s (0.4%)
 NEON LDP/STP copy pldl2strm (64 bytes step)          :  15379.7 MB/s (0.2%)
 NEON LDP/STP copy pldl1keep (32 bytes step)          :  15705.0 MB/s
 NEON LDP/STP copy pldl1keep (64 bytes step)          :  16216.1 MB/s (0.4%)
 NEON LD1/ST1 copy                                    :  16102.1 MB/s (0.2%)
 NEON STP fill                                        :  37033.2 MB/s (1.9%)
 NEON STNP fill                                       :  34190.7 MB/s (2.6%)
 ARM LDP/STP copy                                     :  16468.4 MB/s (1.9%)
 ARM STP fill                                         :  39243.4 MB/s (2.7%)
 ARM STNP fill                                        :  33605.0 MB/s (1.6%)

==========================================================================
== Framebuffer read tests.                                              ==
==                                                                      ==
== Many ARM devices use a part of the system memory as the framebuffer, ==
== typically mapped as uncached but with write-combining enabled.       ==
== Writes to such framebuffers are quite fast, but reads are much       ==
== slower and very sensitive to the alignment and the selection of      ==
== CPU instructions which are used for accessing memory.                ==
==                                                                      ==
== Many x86 systems allocate the framebuffer in the GPU memory,         ==
== accessible for the CPU via a relatively slow PCI-E bus. Moreover,    ==
== PCI-E is asymmetric and handles reads a lot worse than writes.       ==
==                                                                      ==
== If uncached framebuffer reads are reasonably fast (at least 100 MB/s ==
== or preferably >300 MB/s), then using the shadow framebuffer layer    ==
== is not necessary in Xorg DDX drivers, resulting in a nice overall    ==
== performance improvement. For example, the xf86-video-fbturbo DDX     ==
== uses this trick.                                                     ==
==========================================================================

 NEON LDP/STP copy (from framebuffer)                 :   2235.3 MB/s
 NEON LDP/STP 2-pass copy (from framebuffer)          :   1515.1 MB/s
 NEON LD1/ST1 copy (from framebuffer)                 :   2231.8 MB/s
 NEON LD1/ST1 2-pass copy (from framebuffer)          :   1525.6 MB/s
 ARM LDP/STP copy (from framebuffer)                  :   1911.1 MB/s
 ARM LDP/STP 2-pass copy (from framebuffer)           :   1175.7 MB/s

==========================================================================
== Memory latency test                                                  ==
==                                                                      ==
== Average time is measured for random memory accesses in the buffers   ==
== of different sizes. The larger is the buffer, the more significant   ==
== are relative contributions of TLB, L1/L2 cache misses and SDRAM      ==
== accesses. For extremely large buffer sizes we are expecting to see   ==
== page table walk with several requests to SDRAM for almost every      ==
== memory access (though 64MiB is not nearly large enough to experience ==
== this effect to its fullest).                                         ==
==                                                                      ==
== Note 1: All the numbers are representing extra time, which needs to  ==
==         be added to L1 cache latency. The cycle timings for L1 cache ==
==         latency can be usually found in the processor documentation. ==
== Note 2: Dual random read means that we are simultaneously performing ==
==         two independent memory accesses at a time. In the case if    ==
==         the memory subsystem can't handle multiple outstanding       ==
==         requests, dual random read has the same timings as two       ==
==         single reads performed one after another.                    ==
==========================================================================

block size : single random read / dual random read, [MADV_NOHUGEPAGE]
      1024 :    0.0 ns          /     0.0 ns
      2048 :    0.0 ns          /     0.0 ns
      4096 :    0.0 ns          /     0.0 ns
      8192 :    0.0 ns          /     0.0 ns
     16384 :    0.0 ns          /     0.0 ns
     32768 :    0.0 ns          /     0.0 ns
     65536 :    0.0 ns          /     0.0 ns
    131072 :    1.0 ns          /     1.5 ns
    262144 :    2.0 ns          /     2.8 ns
    524288 :    3.0 ns          /     3.9 ns
   1048576 :   19.3 ns          /    27.6 ns
   2097152 :   27.1 ns          /    34.1 ns
   4194304 :   31.9 ns          /    36.2 ns
   8388608 :   37.2 ns          /    37.3 ns
  16777216 :   52.8 ns          /    50.5 ns
  33554432 :  128.8 ns          /   168.6 ns
  67108864 :  194.1 ns          /   228.1 ns

block size : single random read / dual random read, [MADV_HUGEPAGE]
      1024 :    0.0 ns          /     0.0 ns
      2048 :    0.0 ns          /     0.0 ns
      4096 :    0.0 ns          /     0.0 ns
      8192 :    0.0 ns          /     0.0 ns
     16384 :    0.0 ns          /     0.0 ns
     32768 :    0.0 ns          /     0.0 ns
     65536 :    0.0 ns          /     0.0 ns
    131072 :    1.0 ns          /     1.5 ns
    262144 :    1.5 ns          /     2.1 ns
    524288 :    1.8 ns          /     2.4 ns
   1048576 :   17.5 ns          /    26.1 ns
   2097152 :   25.2 ns          /    32.3 ns
   4194304 :   28.9 ns          /    34.3 ns
   8388608 :   31.1 ns          /    35.0 ns
  16777216 :   41.8 ns          /    47.3 ns
  33554432 :  123.6 ns          /   163.9 ns
  67108864 :  175.6 ns          /   210.6 ns
```


## Disk (ZHITAI TiPlus7100 512GB NVMe SSD)
- **Sequential R/W**: ~4.9 GB/s read, ~4.6 GB/s write (PCIe 4.0 x4 performance).
- **4K Random**: Write (203.7 MB/s) is robust; Read (74.5 MB/s) is adequate for daily tasks but a bottleneck for database workloads.
<table>
<thead>
  <tr>
    <th>Test</th>
    <th>Result(MB/s)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>iozone 4K Random Write</td>
    <td>203.7</td>
  </tr> 
  <tr>
    <td>iozone 4K Random Read</td>
    <td>74.5</td>
  </tr> 
  <tr>
    <td>iozone 1M Sequential Write</td>
    <td>4,575.3</td>
  </tr> 
  <tr>
    <td>iozone iozone 1M Sequential Read</td>
    <td>4,911.3</td>
  </tr> 
</tbody>
</table>





## WLAN（Wi-Fi 6 AX210 160MHz）
- **Conclusion**: Near-gigabit wireless speeds in ideal Wi-Fi 6/6E (160MHz) environments.

<table>
<thead>
  <tr>
    <th>Test</th>
    <th>Result(MB/s)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Upload (TX)</td>
    <td>355 Mbits/sec</td>
  </tr> 
  <tr>
    <td>Download (RX)</td>
    <td>215 Mbits/sec</td>
  </tr> 
  <tr>
    <td rowspan="2">Simultaneous</td>
    <td>TX：161 Mbits/sec</td>
  </tr> 
  <tr>
    <td>RX：117 Mbits/sec</td>
  </tr>
</tbody>
</table>



## Conclusion
- The MetaComputing AI PC + Framework Laptop 13 delivers exceptional performance in multi-core CPU tasks, system responsiveness, memory bandwidth, and integrated GPU capabilities—surpassing traditional ARM laptops and competing with x86 thin-and-lights. Its modular design ensures longevity, while benchmarks confirm
