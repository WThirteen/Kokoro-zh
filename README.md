# Kokoro-zh  

这是一个对kokoro-zh的api服务。

原有的Kokoro-Fastapi服务使用的模型为v1.0 而使用该框架无法适配 kokoro-zh版本的模型

根据 https://github.com/remsky/Kokoro-FastAPI/issues/214 无法复现。所以参考了其他方式。


## 配置
* python==3.10
* CUDA==12.4

可先参考huggingface中 用法
https://huggingface.co/hexgrad/Kokoro-82M-v1.1-zh

```
!pip install -q kokoro>=0.8.2 "misaki[zh]>=0.8.2" soundfile
!apt-get -qq -y install espeak-ng > /dev/null 2>&1
from IPython.display import display, Audio

# 国内用户替换为 https://hf-mirror.com/hexgrad/Kokoro-82M-v1.1-zh
!wget https://huggingface.co/hexgrad/Kokoro-82M-v1.1-zh/resolve/main/samples/make_en.py
!python make_en.py
display(Audio('HEARME_en.wav', rate=24000, autoplay=True))

!wget https://huggingface.co/hexgrad/Kokoro-82M-v1.1-zh/resolve/main/samples/make_zh.py
!python make_zh.py
display(Audio('HEARME_zf_001.wav', rate=24000, autoplay=False))

```

