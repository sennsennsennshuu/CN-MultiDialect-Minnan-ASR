# CN-MultiDialect-Minnan-ASR

台湾闽南语（无声调台罗拼音标签）追加学习候选模型，基于 [ASLP-lab/CN-MultiDialect-ASR](https://github.com/ASLP-lab/CN-MultiDialect-ASR)。

> 当前候选状态：`verified_with_probe_warning`。它适合复现、评估和继续研究；不能把探针告警忽略后直接宣称为生产级模型。

## 内容

- `EVALUATION.md`：验证指标、格式检查和 h 错误率对比。
- `metadata/`：交付状态、对比结果和 SABE release 清单。
- `release-manifest.json`：原始候选目录的文件数、大小和 SHA256。
- `SHA256SUMS.txt`：逐文件完整性清单。
- `LICENSE.md`、`NOTICE.md`：上游 ASR 基座及 Apache-2.0 说明。

## 大文件说明

GitHub 仓库只包含 `adapter/` 中的 LoRA 权重与配置，以及评估和完整性元数据。完整 `merged/`、ONNX、GGUF 和其他推理文件由维护者另行上传百度网盘；原始候选目录仍由 `SHA256SUMS.txt` 绑定。GitHub 单个 Release 资产必须小于 2 GiB，因此 4 GiB 级 GGUF 也不适合作为单一 GitHub 资产。

## 基座

- ASR 基座：[ASLP-lab/CN-MultiDialect-ASR](https://github.com/ASLP-lab/CN-MultiDialect-ASR)
- 许可证：Apache-2.0

## 数据集来源

- [Common Voice Scripted Speech 27.0 - Taiwanese (Minnan)](https://mozilladatacollective.com/datasets/cmu5vcwh800aknq07gjqn07ao)
- 许可证：[CC0-1.0](https://spdx.org/licenses/CC0-1.0.html)

## 附加署名请求

建议在使用本项目模型或权重时保留以下文字：

> CN-MultiDialect-Minnan-ASR；基于 ASLP-lab/CN-MultiDialect-ASR；使用 Common Voice Scripted Speech 27.0 - Taiwanese (Minnan)。

该请求不改变 CC0-1.0 的法律授权范围。

