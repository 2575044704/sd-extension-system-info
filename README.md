# 为 SD Automatic WebUI 的系统信息选项卡扩展
## 使用注意：请先安装nvidia-smi库，可以通过这条命令安装：'''pip install nvidia-ml-py3 '''
## 基于vlad作者的系统信息插件，做出了更完善的更新：

*更新包括*：
 - 新增显示GPU温度，GPU利用率等
 - 对某些数值进行了中文翻译，免得看不懂
 - 为这个插件增加了API调用，可以随时导出系统运行状态，方便故障排查。特别是运用于大型AI绘画网站里

   
*未来打算的更新：*

  - 增加显卡温度过高自动报警，防止GPU过热导致爆炸

# 截图
---
## 第一栏：服务器及运行时间
![image](https://github.com/2575044704/sd-extension-system-info/assets/19410065/6de11e09-092a-4607-97c6-fd064aae5e0a)
## 第二栏：服务器显存利用率和显卡温度
![image](https://github.com/2575044704/sd-extension-system-info/assets/19410065/de99816a-2332-4ca1-b5c0-cebf49cee052)
## 完整截图：
![image](https://github.com/2575044704/sd-extension-system-info/assets/19410065/763dd1b8-889e-4361-b4a9-e3a4f0790153)

---


  
在自动 WebUI 中创建顶级 **系统信息** 选项卡，其中包括：

*注意*：

- 如果选项卡可见，则状态和内存信息会每秒自动更新  
  （当选项卡不可见时不会执行更新）  
- 所有其他信息在 WebUI 加载时仅更新一次，并且  
  如果需要，可以强制刷新  

## 当前信息

- 服务器启动时间
- 版本
- 当前模型和VAE（变分自编码器）
- 当前状态
- 当前内存统计

## 系统数据

- 平台详细信息
- Torch、CUDA 和 GPU 详细信息
- 活动 CMD 标志，如 `low-vram` 或 `med-vram`
- 重要库的版本，如 `xformers`、`transformers` 等
- 依赖库的版本，如 `k-diffusion` 等

![截图](system-info.jpg)

## 基准测试

- 允许运行标准化基准测试，并可选择将数据提交给云记录器 [[详情]](pages/README.md)

![截图](benchmark.jpg)

- *注意：如果系统属性中有任何更改，则会追加记录，否则基准数据将替换现有的匹配记录*

- 所有结果都可以在[在线查看](https://vladmandic.github.io/sd-extension-system-info/pages/benchmark.html)

## 模型

- 模型（带哈希）
- 超网络
- 嵌入（包括每个嵌入向量的数量信息）

  ![截图](system-info-models.jpg)

## 信息对象

- 系统对象可作为 JSON 使用，用于快速传递信息

  ![截图](system-info-json.jpg)
