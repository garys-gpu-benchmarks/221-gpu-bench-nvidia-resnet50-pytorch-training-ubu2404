# Results: 221 ResNet-50 FP16 Training Step (PyTorch)

**Main goal:** Measure mixed-precision ResNet-50 training-step efficiency  
**Tools:** Run scripts/train_resnet50.py via collect_resnet50_train.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_138 · recorded 2026-11-12). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 NVL (95830 MiB) · AMD EPYC 9374F 32-Core Processor · Ubuntu 24.04.5 LTS · kernel 6.8.0-138-generic · driver 595.91.07
- **Run:** 2026-11-12T23:12:34Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 01:10 · benchmark 00:09 · whole run 01:31
- **Source:** run 221_20261112_231234
- **Command:** `bash run_benchmark.sh --smoke --precision fp16 --image-size 64 --batch-size 2 --learning-rate 0.1 --warmup-iters 1 --num-iterations 3`

| # | Metric | Result |
|---|---|---|
| 1 | Training batch step time (step_time_msec) | 12.241866 |
| 2 | Training throughput (images_per_sec) | 163.98630866666667 |
| 3 | Modeled FP16 training throughput, 3x forward FLOPs, TFLOP/s (fp16_tflops) | 0.30521533333333334 |
| 4 | Peak GPU memory (peak_gpu_memory_gb) | 0.281045 |
| 5 | Modeled weight and feature-map traffic, GB/s (modeled_weight_feature_traffic_gb_s) | 29.401505333333333 |
<!-- /profile:smoke -->
