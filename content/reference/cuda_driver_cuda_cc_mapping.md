# CUDA Driver, Toolkit, and Compute Capability Mapping (2026)

This table uses NVIDIA's "CUDA Toolkit and Corresponding Driver Versions"
values for Linux x86_64. These are the toolkit-corresponding driver versions,
not the lower CUDA minor-version compatibility floor. For CUDA minor-version
compatibility, CUDA 12.x requires driver >= 525 and < 580, while CUDA 13.x
requires driver >= 580.

Abbreviations: GA = General Availability, the first official public release of
a CUDA version. U1 = Update 1, the first update release after GA.

  | CUDA     | Toolkit Linux Driver | Driver Branch | Architecture / Compute Capability Notes                               |
  | -------- | -------------------- | ------------- | ---------------------------------------                               |
  | 12.0 GA  | 525.60.13            | R525          | Maxwell and newer; adds Hopper (CC 9.0)                               |
  | 12.1 GA  | 530.30.02            | R530          | Maxwell and newer; Hopper supported                                   |
  | 12.2 GA  | 535.54.03            | R535          | Maxwell and newer; Hopper supported                                   |
  | 12.3 GA  | 545.23.06            | R545          | Maxwell and newer; Hopper supported                                   |
  | 12.4 GA  | 550.54.14            | R550          | Maxwell and newer; Hopper supported                                   |
  | 12.5 GA  | 555.42.02            | R555          | Maxwell and newer; Hopper supported                                   |
  | 12.6 GA  | 560.28.03            | R560          | Maxwell and newer; Hopper supported                                   |
  | 12.8 GA  | 570.26               | R570          | Maxwell/Pascal/Volta deprecated; adds Blackwell SM 100/101/120        |
  | 12.8 U1  | 570.124.06           | R570          | Same CUDA 12.8 family                                                 |
  | 12.9 GA  | 575.51.03            | R575          | CUDA 12.x still supports Maxwell/Pascal/Volta; adds SM 103 and SM 121 |
  | 12.9 U1  | 575.57.08            | R575          | Same CUDA 12.9 family                                                 |
  | 13.0 GA  | 580.65.06            | R580          | Drops Maxwell/Pascal/Volta; minimum Turing (CC 7.5)                   |
  | 13.1 GA  | 590.44.01            | R590          | Turing and newer                                                      |
  | 13.2 GA  | 595.45.04            | R595          | Turing and newer                                                      |
  | 13.3 GA  | 610.43.02            | R610          | Turing and newer                                                      |

## Compute Capability Mapping

  | CC        | Architecture         | Typical GPUs                            |
  | ----      | -------------        | --------------                          |
  | 5.0 / 5.2 | Maxwell              | GTX 750 Ti, GTX 980                     |
  | 6.x       | Pascal               | GTX 1080 Ti, P100                       |
  | 7.0       | Volta                | V100                                    |
  | 7.5       | Turing               | RTX 2080, T4                            |
  | 8.0       | Ampere               | A100                                    |
  | 8.6       | Ampere               | RTX 3090, RTX 3080                      |
  | 8.9       | Ada                  | RTX 4090, L40S                          |
  | 9.0       | Hopper               | H100, H200                              |
  | 10.0      | Blackwell Datacenter | B200, GB200                             |
  | 10.3      | Blackwell Ultra      | B300, GB300                             |
  | 11.0      | Thor / Jetson        | Jetson T5000, Jetson T4000              |
  | 12.0      | Blackwell RTX        | RTX 5090, 5080, 5070, RTX PRO Blackwell |
  | 12.1      | GB10                 | NVIDIA GB10, DGX Spark                  |

## CUDA 13 Changes

CUDA 13 drops support for:
- Maxwell (CC 5.x)
- Pascal (CC 6.x)
- Volta (CC 7.0)

Minimum supported architecture: Turing (CC 7.5).

## Driver 535.274.02

  | Driver     | Practical Notes                                                                                                                                                                                                                                    |
  | ---------- | ---------------                                                                                                                                                                                                                                    |
  | 535.274.02 | R535 driver. It is new enough for CUDA 12.x minor-version compatibility, but the newest toolkit-corresponding driver in R535 is CUDA 12.2. For full support of newer CUDA 12.x toolkit/driver features, use the corresponding newer driver branch. |

## Recommended Stacks (2026)

Treat these as conservative examples, not universal truth. Production clusters
should use the latest certified data-center driver for the GPU, OS, and CUDA
toolkit being deployed.

  | GPU             | Recommended Driver  | CUDA          |
  | ------          | ------------------- | ------        |
  | A100 / H100     | R570+ or R580+      | 12.8+ or 13.x |
  | L40S / RTX 4090 | R570+ or R580+      | 12.8+ or 13.x |
  | RTX 5090        | R580+               | 13.x          |
  | B200 / GB200    | R580+               | 13.x          |

## Sources

- NVIDIA CUDA Toolkit Release Notes, "CUDA Toolkit and Corresponding Driver Versions": https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html
- NVIDIA CUDA 12.8 Release Notes, deprecated architectures and Blackwell targets: https://docs.nvidia.com/cuda/archive/12.8.0/cuda-toolkit-release-notes/index.html
- NVIDIA CUDA 12.9 Release Notes, SM 103/121 support and CUDA 12.x architecture deprecation notice: https://docs.nvidia.com/cuda/archive/12.9.0/cuda-toolkit-release-notes/index.html
- NVIDIA CUDA GPU Compute Capability table: https://developer.nvidia.com/cuda/gpus
- NVIDIA Legacy CUDA GPU Compute Capability table: https://developer.nvidia.com/cuda/gpus/legacy
