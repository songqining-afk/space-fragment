# 专属空间碎片 · Space Fragment

> 用一句话描述想象中的空间，10 万级粒子实时采样图像像素并重组为可交互的 3D 形态。  
> 本仓库为 **Demo 版**：在线体验使用预设样例图，完整 AI 文生图流程见下方演示视频。

**体验方式：** 克隆后本地运行（见下方），或观看完整流程演示视频。

**完整流程演示视频：**

https://media.70-studio.com/space-fragment.mp4

---

## 项目简介

「Space Fragment / 专属空间碎片」是一个建筑 × AI 交互实验：用户输入空间构想，AI 生成空间意象，Three.js 驱动粒子从流动场 morph 到图像采样网格，支持拖拽旋转、粒子扰动与 JPEG 导出。

| 能力 | Demo 版（本仓库） | 完整版（视频展示） |
|------|-------------------|-------------------|
| Scene 1 粒子流场 | ✅ | ✅ |
| Scene 2 粒子拼图 morph | ✅（预设样例图） | ✅（HF FLUX 实时生成） |
| 鼠标交互 / 导出 JPEG | ✅ | ✅ |
| 自定义文生图 | — | ✅ Hugging Face FLUX.1-schnell |

---

## 技术栈

- **前端：** 原生 HTML / CSS / JavaScript（单页 `index.html`）
- **3D：** Three.js + WebGL Shader + EffectComposer / UnrealBloomPass
- **噪声场：** simplex-noise
- **Demo 样例：** `demo/sample.jpg`（仓库内置，无 API 依赖）

---

## 目录结构

```
space-fragment/
├── index.html          # 主站（单页应用）
├── demo/
│   └── sample.jpg      # Demo 预设空间意象（粒子采样源）
├── package.json
└── README.md
```

---

## 本地运行

```bash
# 克隆后进入目录
npm run dev
# 或
npx serve .
```

浏览器打开终端提示的地址（如 `http://localhost:3000`），点击 **TRY DEMO / 体验 Demo**。

> 勿直接用 `file://` 打开 HTML，部分浏览器会拦截 `fetch` 加载 demo 图片。

---

## Demo 模式说明

公开仓库 **不包含** Hugging Face API Token，也不调用外部 AI 接口：

1. 用户可输入空间描述（增强沉浸感），或留空自动填入默认文案
2. 点击 Demo 后加载 `demo/sample.jpg`
3. 粒子系统执行与完整版相同的 Scene 2 morph、交互与导出

完整 AI 文生图流程（FLUX.1-schnell + 中文翻译 + 粒子重组）见顶部演示视频。

若需自建完整版，可在私有分支接入 Hugging Face Inference API，Token 仅通过服务端环境变量下发，**勿写入前端或公开仓库**。

---

## 作者

**宋齐宁（Quini）** · 建筑设计 × AI 交互

---

## License

Private · All rights reserved
