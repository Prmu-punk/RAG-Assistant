## 本地 App（轻量 Web UI）

这个 App **不修改项目任何现有代码**，仅新增 `local_app/` 与 `run_local_app.py`。

### 启动

在项目根目录执行：

```bash
python run_local_app.py
```

默认会打开浏览器：`http://127.0.0.1:8848/`

参数：

- `--host 0.0.0.0`：局域网访问（谨慎）
- `--port 9000`：自定义端口
- `--no-browser`：不自动打开浏览器

### 功能

- 对话聊天（RAG 检索 + 大模型生成）
- 展示本轮引用来源（文件名/页码 + 片段）
- 生成参数：`top_k` / `temperature` / `max_tokens`
- 系统状态：向量库是否存在、collection 文档数
- 一键“重建知识库”（后台运行 `process_data.main()`，可查看日志）

### 常见问题

- **Docs=0 / 向量库不存在**：先点击“重建知识库”，或确认 `./data` 里已有课程文件（PDF/PPTX/DOCX/TXT）。
- **OpenAI/Embedding 报错**：检查 `config.py` 中 `OPENAI_API_KEY` / `OPENAI_API_BASE` / 模型名称是否可用。


