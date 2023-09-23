# llm-notebooks

This repository serves as a guide for learners who want to run LLM models locally on their home PC / workstation.The notebooks within have the following system requirements.The notebooks in
this repository is a re-production of various published articles I have learned from, and find enlightening to use as exercises for learning.

GPU: Minimum VRAM of 10gb is required; e.g NVIDIA RTX 3080 is sufficient.
OS: Debian / Ubuntu
CPUs: Recommended 8c/16t
Memory: Recommended 32gb of memory.
Filesystem: Minimum of 20gb for storing datasets and LLM data (weights and biases).

Software:
- python 3.10.11
- nvidia-drivers
   - nvidia-driver                         535.104.05-1
	 - cuda                                  12.2.2-1
	 - nvidia-support                        20151021+13

The notebooks use the Falcon family of LLMs, specifically the falcon-7b series.

## Getting started

Install required Python dependencies

```bash
$ python3 -m venv .venv
$ source .venv/bin/activate
(.venv)$ pip install -r requirements.txt
```

Start JupyterLab

```bash
$ juypter-lab
```


## Notebooks


### day-0: Apply Quantization to Falcon-7b, prompting with Langchain

**Main Reading**: [Private LLM](https://vilsonrodrigues.medium.com/run-your-private-llm-falcon-7b-instruct-with-less-than-6gb-of-gpu-using-4-bit-quantization-ff1d4ffbabcc)

In the `day-0` notebook, we go over the following elementary tasks of running the Falcon 7b Instruct LLM locally for Question & Answering queries.

1) Download **Falcon-7b** from HuggingFace.
2) Apply Quantization so that the LLM can fit into our consumer GPU.
3) Handle question and answer queries with Huggingface Pipeline
4) Simple prompting with Langchain.

**Supplementary Readings**:
https://huggingface.co/blog/hf-bitsandbytes-integration
https://huggingface.co/blog/4bit-transformers-bitsandbytes
https://huggingface.co/docs/optimum/concept_guides/quantization
https://pytorch.org/docs/stable/quantization.html


### day-1: Building a mental-health chatbot
