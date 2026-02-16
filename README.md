# Qwen3.5

<div style="text-align: center">
  <img width="400px" src="https://qianwen-res.oss-accelerate.aliyuncs.com/logo_qwen3.5.png">
  <p>
    <a href="https://chat.qwen.ai/">💜 <b>Qwen Chat</b></a> |
    <a href="https://huggingface.co/Qwen">🤗 Hugging Face</a> | 
    <a href="https://modelscope.cn/organization/qwen">🤖 ModelScope</a> | 
    📑 Paper |
    <a href="https://qwen.ai/blog?id=qwen3.5">📑 Blog</a> |
    📖 Documentation |
    <a href="https://github.com/QwenLM/Qwen/blob/main/assets/wechat.png">💬 WeChat (微信)</a> |
    <a href="https://discord.gg/CV4E9rpNSD">🫨 Discord</a>   
  </p>
</div>

Welcome to the GitHub repository of Qwen3.5. Here, you can find official information about Qwen3.5 (User Guide, coming soon), post your questions ([Issues](https://github.com/QwenLM/Qwen3.5/issues)), and share your ideas with the community ([Discussions](https://github.com/QwenLM/Qwen3.5/discussions)).

## Introduction

Over recent months, we have intensified our focus on developing foundation models that deliver exceptional utility and performance. Qwen3.5 represents a significant leap forward, integrating breakthroughs in multimodal learning, architectural efficiency, reinforcement learning scale, and global accessibility to empower developers and enterprises with unprecedented capability and efficiency.

Qwen3.5 features the following enhancement:

- **Unified Vision-Language Foundation**: Early fusion training on trillions of multimodal tokens achieves cross-generational parity with Qwen3 and outperforms Qwen3-VL models across reasoning, coding, agents, and visual understanding benchmarks.

- **Efficient Hybrid Architecture**: Gated Delta Networks combined with sparse Mixture-of-Experts deliver high-throughput inference with minimal latency and cost overhead.

- **Scalable RL Generalization**: Reinforcement learning scaled across million-agent environments with progressively complex task distributions for robust real-world adaptability.

- **Global Linguistic Coverage**: Expanded support to 201 languages and dialects, enabling inclusive, worldwide deployment with nuanced cultural and regional understanding.

- **Next-Generation Training Infrastructure**: Near-100% multimodal training efficiency compared to text-only training and asynchronous RL frameworks supporting massive-scale agent scaffolds and environment orchestration.


## News

- 2026-02-16: We release Qwen3.5. The first release includes a 397B-A17B MoE model. Read more on our [release blog](https://qwen.ai/blog?id=qwen3.5). More sizes are coming & Happy Chinese New Year!
- 2025-09-11: We release Qwen3-Next-80B-A3B, an ultra-sparse mixture-of-experts model with hybrid attention architecture, designed for extreme efficiency. Read more on our [blog](https://qwen.ai/blog?id=qwen3-next)

## Models

The official model weights are released on:
- [🤗Hugging Face Hub](https://huggingface.co/Qwen): Most LLM frameworks and applications support downloading model files from Hugging Face Hub automatically by specifying the model ID, e.g., `Qwen/Qwen3.5-397B-A17B`. 
  You can also download model files manually using `huggingface download` or `git clone`.
  Please follow the instructions on the model page. 
- [🤖ModelScope](https://www.modelscope.cn/organization/Qwen): For users unable to access Hugging Face Hub, we strongly recommend using ModelScope. 
  For supported frameworks, you can download from ModelScope by setting environment variables, such as `SGLANG_USE_MODELSCOPE=true` or `VLLM_USE_MODELSCOPE=true`.
  You can also download model files manually using `modelscope download` or `git clone`.
  Please follow the instructions on the model page. 

## Benchmarks

![Benchmark Results](https://qianwen-res.oss-accelerate.aliyuncs.com/Qwen3.5/Figures/qwen3.5_397b_a17b_score.png)

For detailed results, please check out the [release blog](https://qwen.ai/blog?id=qwen3.5).

## Quickstart

To learn more about Qwen3.5, feel free to read our documentation (coming soon).

### Official

You can try Qwen3.5 on our official sites and enjoy the native experience with extra features, such as deep research, web dev, and adaptive tool use.

#### Qwen Chat

For users who simply would like to try Qwen3.5, [Qwen Chat](https://chat.qwen.ai) is just a touch away. 
Qwen Chat provides Web UI and desktop and mobile applications, with a familiar, easy-to-use user interface.
Qwen Chat is also a playground for our ideas, showcasing how Qwen3.5 can be integrated into your workflow and applications.

#### Qwen API

The official Qwen API is provided by [Alibaba Cloud Model Studio](https://modelstudio.alibabacloud.com/).

Alibaba Cloud Model Studio provides first-class support for Qwen3.5, which is compatible with various API specifications, including OpenAI and Anthropic, making it simple for you to try Qwen3.5 in your own applications.

#### Qwen Code

[Qwen Code](https://github.com/QwenLM/qwen-code) is an open-source AI agent for the terminal, optimized for Qwen models. It helps you understand large codebases, automate tedious work, and ship faster.

For more information, please refer to [Qwen Code](https://qwenlm.github.io/qwen-code-docs/).

#### Qwen Agent

For agent development, take a look at [Qwen-Agent](https://github.com/QwenLM/Qwen-Agent). Qwen Agent is an open-source AI agent framework that helps you build powerful LLM applications based on the instruction following, tool usage, planning, and memory capabilities of Qwen.

Check out [Qwen Agent](https://qwenlm.github.io/Qwen-Agent/en/) to find out more!

### Local Use

#### Hugging Face Transformers

[`transformers`](https://huggingface.co/transformers) acts as the model-definition framework in the current open-weight LLM landscape.
It also includes functionalities for LLM inference and training. The addition of serving capabilities in `transformers` makes it much easier to integrate new models in your development.

To launch a server, simply use the `transformers serve` command:
```shell
transformers serve --port 8000 --continuous-batching
```
OpenAI-compatible APIs can be accessed at `http://localhost:8000/v1` and the server downloads models from Hugging Face Hub automatically.

With the server running, you can also interact with Qwen3.5 directly from the command line:
```shell
transformers chat Qwen/Qwen3.5-397B-A17B
```

#### llama.cpp

[`llama.cpp`](https://github.com/ggml-org/llama.cpp) enables LLM inference with minimal setup and state-of-the-art performance on a wide range of hardware.
llama.cpp supports Qwen3.5 (text & vision).
Look for models ending with GGUF on Hugging Face Hub.

#### MLX LM

If you are running on Apple Silicon, [`mlx-lm`](https://github.com/ml-explore/mlx-lm) also supports Qwen3.5 (text-only). 
Look for models ending with MLX on Hugging Face Hub.

### Deployment

Qwen3.5 is supported by multiple inference frameworks. 
Here we demonstrate the usage of `SGLang` and `vLLM`

#### SGLang

[SGLang](https://github.com/sgl-project/sglang) is a fast serving framework for large language models and vision language models.
SGLang could be used to launch a server with OpenAI-compatible API service. 

```shell
python -m sglang.launch_server --model-path Qwen/Qwen3.5-397B-A17B --port 8000 --tp-size 8 --context-length 262144 --reasoning-parser qwen3
```

An OpenAI-compatible API will be available at `http://localhost:30000/v1`.

#### vLLM

[vLLM](https://github.com/vllm-project/vllm) is a high-throughput and memory-efficient inference and serving engine for LLMs.
vLLM could be used to launch a server with OpenAI-compatible API service. 

```shell
vllm serve Qwen/Qwen3.5-397B-A17B --port 8000 --tensor-parallel-size 8 --max-model-len 262144 --reasoning-parser qwen3
```

An OpenAI-compatible API will be available at `http://localhost:8000/v1`.


### Finetuning

We advise you to use training frameworks, including [UnSloth](https://github.com/unslothai/unsloth), [Swift](https://github.com/modelscope/swift), [Llama-Factory](https://github.com/hiyouga/LLaMA-Factory), etc., to finetune your models with SFT, DPO, GRPO, etc.


## License Agreement

All our open-weight models are licensed under Apache 2.0. 
You can find the license files in the respective Hugging Face repositories.

## Citation

If you find our work helpful, feel free to give us a cite.

```bibtex
@misc{qwen3.5
    title  = {{Qwen3.5}: Towards Native Multimodal Agents},
    author = {{Qwen Team}},
    month  = {February},
    year   = {2026},
    url    = {https://qwen.ai/blog?id=qwen3.5}
}
```

## Contact Us
If you are interested to leave a message to either our research team or product team, join our [Discord](https://discord.gg/z3GAxXZ9Ce) or [WeChat groups](https://github.com/QwenLM/Qwen3/blob/main/assets/wechat.png)!
