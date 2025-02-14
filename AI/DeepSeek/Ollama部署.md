# Ollama部署
目前DeepSeek R1及其蒸馏模型均支持使用ollama进行调用，可以在模型主页查看调用情况：[https://ollama.com/library/deepseek-r1](https://ollama.com/library/deepseek-r1)

### 安装Ollama
以linux系统为例，安装命令如下：
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

### 运行
 * 安装完`Ollama`后，可以使用`ollama run`命令自动下载模型权重并且运行模型，或者手动下载指定模型GGUF格式，然后注册到ollama服务，在进行调用
 * 安装完成后，可以使用`ollama serve`来启动服务, 默认端口为11434，可通过环境变量`OLLAMA_HOST`指定端口，例如`OLLAMA_HOST=127.0.0.1:11434`

#### 使用`ollama run`自动下载权重并且运行
以1.5b为例，执行如下命令
```bash
ollama run deepseek-r1:1.5b
```
下载完成后，会自动运行


#### 手动下载权重并且注册到ollama服务
除了使用ollama run命令外， ollama也支持调用手动下载的自定义模型，但需要是GGUF格式。目前
DeepSeek-R1-Distill-Qwen-1.5B模型已有各种不同量化版本的GGUF模型在魔搭社区中上线了：[https://modelscope.cn/search?search=DeepSeek-R1-Distill-Qwen-1.5B-GGUF](https://modelscope.cn/search?search=DeepSeek-R1-Distill-Qwen-1.5B-GGUF)

 * 下载GGUF格式权重
 ```bash
 mkdir DeepSeek-R1-1.5B-GGUF
 modelscope download --model unsloth/DeepSeek-R1-Distill-Qwen-1.5B-GGUF DeepSeek-R1-Distill-Qwen-1.5B-Q4_K_M.gguf --local_dir ./DeepSeek-R1-1.5B-GGUF
 ```

 * 注册模型
 创建一个文件用于注册，文件内容如下：
 ```bash
 # 比如文件名称为 ModelFile, 文件内容为刚刚下载的模型地址
 FROM ./DeepSeek-R1-1.5B-GGUF/DeepSeek-R1-Distill-Qwen-1.5B-Q4_K_M.gguf
 ```

 * 使用如下命令，将该模型加入到ollama本地模型列表，并且运行
 ```bash
 ollama create DeepSeek-R1-1.5B -f ModelFile
 
 # 执行list命令，查看本地模型列表
 ollama list

 # 执行run命令，运行模型
 ollama run DeepSeek-R1-1.5B
 ```