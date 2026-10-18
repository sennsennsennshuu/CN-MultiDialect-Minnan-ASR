# 台湾闽南语 ASR 候选模型

这是基于 `CN-MultiDialect-ASR` 和旧适配器 `recovered-1791690482` 的联合 LoRA 第 32 步候选。它经过云端 FP32 合并、全量 3000 条原验证集成对复核，以及 独立 dev/test 独立复核。

## 复核结果

| 指标 | 旧模型 | 候选模型 |
|---|---:|---:|
| 原验证未见锚点 target score | 0.09487820 | 0.09138832 |
| 原验证未见锚点 SER | 0.02289990 | 0.02233307 |
| 原验证未见锚点 h 错误率 | 0.16108453 | 0.15629984 |
| 独立 dev SER | 0.15904079 | 0.15807607 |
| 独立 test SER | 0.23556009 | 0.23424737 |

格式错误和截断在完整复核中均为 0。候选在训练探针上的目标分数没有改善，因此交付状态明确标为 `verified_with_probe_warning`；这条警告不能被解释为训练集指标改善。

## 文件

- `merged/`：可直接由 Transformers/Qwen3-ASR 加载的 FP32 合并模型。
- `adapter/`：第 32 步 LoRA 推理适配器。
- `comparison.json`：完整验证、训练探针和交付状态。
- `artifact-audit.json`：云端交付文件 SHA256 审计；本地已下载文件均已核对一致。
- `dev/comparison.json`、`test/comparison.json`：独立集成对照摘要。

原有旧模型 release 未覆盖。转换为 SABE 使用的 ONNX/GGUF 前，应保留本目录作为可回退源，并重新执行本地真实推理冒烟测试。
