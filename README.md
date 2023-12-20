# NjRAA Work-in-progress GPU Driver Foundation

`[nee-jee-ray]` stands for `Not just Renamed AMD API`

What we are doing here is a GPU driver as a prototype for future graphics stack of the [@GreenteaOS](https://github.com/GreenteaOS)

<p align="center">
  <a href="https://github.com/sponsors/PeyTy">
    <img width="224px" src="https://raw.githubusercontent.com/GreenteaOS/NjRAA/kawaii/docs/njraa.png" />
  </a>
</p>

- Vulkan
- DirectX / Direct3D
- OpenGL
- OpenCL

Uses safe programming language Hexa.

#### Aim

<p align="center">
  <a href="https://github.com/sponsors/PeyTy">
    <img src="https://raw.githubusercontent.com/GreenteaOS/NjRAA/kawaii/docs/arch.png" />
  </a>
</p>

To support AMD GCN 1.0+ GPUs. And Intel/Nvidia ones that conform to
[Resource binding Tier 3 and Resource heap Tier 2](https://en.wikipedia.org/wiki/Feature_levels_in_Direct3D#Support_matrix).

Later GCN/RDNA GPUs will reuse huge parts of GCN 1.0 code.

Investigate three ways of implementing things. You are welcome to participate at any one you feel comfortable:
- Use NT GPU drivers
	- Note that means using closed-source third-party software
	- Implementing Vulkan ICD and then use it in tandem with DXVK seems like the most approachable way
- Use Mesa open-source drivers
	- This one requires libDRM compatible API implementation
- Write own GPU drivers
	- Mostly depends on DMA mapping and command stream (modern GPUs)

#### Supported GPUs

Depends on the available hardware. You may sponsor this project for broader testable hardware.
<!--
- [ ] [**`AMD Radeon R7 200 Series`**](https://www.techpowerup.com/gpu-specs/radeon-r7-250.c2459) `PCI\VEN_1002&DEV_6610&REV_00` **`Oland GFX6 (gfx601)`**
- [ ] [**`Radeon RX 5500 XT`**](https://www.techpowerup.com/gpu-specs/radeon-rx-5500-xt.c3468) `PCI\VEN_1002&DEV_7340&REV_C5` **`Navi GFX10 (gfx1012)`**
- [ ] [**`Intel(R) HD Graphics 500`**](https://en.wikipedia.org/wiki/Intel_Graphics_Technology#Apollo_Lake) `PCI\VEN_8086&DEV_5A85&REV_0B` **`Gen. 9 (Skylake)`**
- [ ] [**`Intel(R) UHD Graphics 630`**](https://en.wikipedia.org/wiki/Intel_Graphics_Technology#Kaby_Lake_Refresh_/_Amber_Lake_/_Coffee_Lake_/_Coffee_Lake_Refresh_/_Whiskey_Lake_/_Comet_Lake) `PCI\VEN_8086&DEV_TBA&REV_TBA` **`Gen. 9.5 (Kaby Lake)`**
- [ ] [**`Intel(R) UHD Graphics 750`**](https://en.wikipedia.org/wiki/Intel_Graphics_Technology#Twelfth_generation_(Gen12)) `PCI\VEN_8086&DEV_TBA&REV_TBA` **`Gen. 12 (Rocket Lake-S)`**
- [ ] [**`Intel(R) Iris(R) Xe Graphics`**](https://en.wikipedia.org/wiki/Intel_Graphics_Technology#Twelfth_generation_(Gen12)) `PCI\VEN_8086&DEV_TBA&REV_TBA` **`G7 Gen. 12 (Tiger Lake-U)`**
-->

#### Step by step goals

- [ ] Create IOCTL API to control the driver from userspace
- [ ] Init GPU engine and setup command buffer
- [ ] Mode setting
- [ ] Draw anything on screen

<!--
#### Limitations

Only fullscreen applications supported, no desktop GUI!
Use only for secondary GPU with extra screen
(or use extra inputs and switch dynamically).
-->

#### Build

Follow build instructions from the [Tofita](https://github.com/GreenteaOS/Tofita) repo.

#### License

GNU LESSER GENERAL PUBLIC LICENSE Version 3
