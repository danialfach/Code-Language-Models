# Quick Start
## Requirements
Make sure you have `python>=3.9` installed before using it. To set up the environment and install the requirements, run the following command: 
```bash
git clone https://github.com/danialfach/Code-Language-Models.git
cd Code-Language-Models
pip install -r requirements.txt
```
## Ollama
You can run Yi-Coder on Ollama locally.

1. After [installing Ollama](https://ollama.com/), you can start the Ollama service. Note that keep this service running while you use Ollama.

    ```python
    ollama serve
    ```

2. Run Yi-Coder models. For more Yi models supported by Ollama, see [Yi tags](https://ollama.com/library/yi/tags).

    ```python
    ollama run yi-coder
    ```

# Results

For the highlight of full results, please refer to our [blog post](https://01-ai.github.io/blog.html?post=en/2024-09-05-A-Small-but-Mighty-LLM-for-Code.md).
Below we present more detailed results for multilingual HumanEval, CodeEditorBench, and math programming.

## Multi-lingual HumanEval
1) Base model comparison

| Model                     | Size  | Python | C++   | Java  | PHP   | TS    | C#    | Bash  | JS    | Avg   |
|---------------------------|-------|--------|-------|-------|-------|-------|-------|-------|-------|-------|
| CodeLLama                  | 34B   | 48.2   | 44.7  | 44.9  | 41.0  | 42.1  | 48.7  | 15.8  | 42.2  | 41.0  |
| StarCoder2                 | 15B   | 46.3   | 41.4  | 33.9  | 39.5  | 43.8  | 29.2  | 18.9  | 44.2  | 37.2  |
| DeepSeek-Coder-Base        | 1.3B  | 34.8   | 31.1  | 32.3  | 24.2  | 28.9  | 36.7  | 10.1  | 28.6  | 28.3  |
| DeepSeek-Coder-Base        | 6.7B  | 49.4   | 50.3  | 43.0  | 38.5  | 49.7  | 50.0  | 28.5  | 48.4  | 44.7  |
| DeepSeek-Coder-Base        | 33B   | **56.1**   | 58.4  | **51.9**  | 44.1  | 52.8  | 51.3  | 32.3  | **55.3**  | **50.3**  |
| CodeQwen1.5                | 7B    | 52.4   | 52.2  | 42.4  | **46.6**  | 52.2  | 55.7  | **36.7**  | 49.7  | 48.5  |
| Yi-Coder                   | 1.5B  | 41.5   | 37.9  | 32.9  | 34.2  | 35.9  | 38.6  | 8.9   | 39.1  | 33.6  |
| Yi-Coder                   | 9B    | 53.7   | **59.6**  | 36.7  | 45.3  | **57.9**  | **58.2**  | 30.4  | 54.7  | 49.6  |

2) Instruction-tuned model comparison

| Model                     | Size  | Python | C++   | Java  | PHP   | TS    | C#    | Bash  | JS    | Avg   |
|---------------------------|-------|--------|-------|-------|-------|-------|-------|-------|-------|-------|
| GPT-4                      |       | 84.1   | 76.4  | 81.6  | 77.2  | 77.4  | 79.1  | 58.2  | 78.0  | 76.5  |
| DeepSeek-Coder-Instruct     | 1.3B  | 65.2   | 45.3  | 51.1  | 45.3  | 59.7  | 55.1  | 12.7  | 52.2  | 48.4  |
| DeepSeek-Coder-Instruct     | 6.7B  | 78.9   | 63.4  | 68.4  | 68.9  | 67.2  | 72.8  | 36.7  | 72.7  | 66.1  |
| DeepSeek-Coder-Instruct     | 33B   | 79.3   | 68.9  | 73.4  | 72.7  | 67.9  | 74.1  | 43.0  | 73.9  | 69.2  |
| CodeQwen1.5-Chat            | 7B    | 83.2   | **71.2**  | 70.1  | **73.5**  | **75.4**  | 75.9  | 41.1  | 78.2  | 71.1  |
| Yi-Coder-Chat               | 1.5B  | 67.7   | 49.1  | 51.9  | 52.2  | 57.9  | 57.6  | 19.0  | 59.6  | 51.9  |
| Yi-Coder-Chat               | 9B    | **85.4**   | 67.7  | **76.0**  | 72.1  | 72.3  | **76.6**  | **45.6**  | **78.9**  | **71.8**  |

## CodeEditorBench
1) Primary

| Models                 | Debug  | Translation | Switch | Polish | Avg Win Rate |
| ---------------------- | ------ | ----------- | ------ | ------ | ------------ |
| GPT-4                  | 49.30% | 50.30%      | 26.40% | 1.33%  | 85.72%       |
| Yi-Coder-9B-Chat       | 46.09% | 42.60%      | 14.06% | 7.04%  | 78.57%       |
| DS-Coder-33B-Instruct  | 48.70% | 45.10%      | 16.20% | 1.14%  | 67.86%       |
| CodeQwen1.5-7B-Chat    | 42.37% | 34.20%      | 11.37% | 5.03%  | 57.14%       |
| GLM-4                  | 27.10% | 36.50%      | 8.50%  | 6.46%  | 50.00%       |
| CodeLLaMA-13B-Instruct | 36.80% | 27.50%      | 2.10%  | 1.82%  | 39.29%       |
| CodeLLaMA-7b-Instruct  | 33.60% | 23.10%      | 1.70%  | 1.17%  | 21.43%       |

2) Plus

| Models                 | Debug  | Translation | Switch | Polish | Avg Win Rate |
| ---------------------- | ------ | ----------- | ------ | ------ | ------------ |
| GPT-4                  | 31.60% | 46.50%      | 26.40% | 1.12%  | 82.14%       |
| Yi-Coder-9B-Chat       | 26.44% | 34.91%      | 14.06% | 5.87%  | 75.00%       |
| DS-Coder-33B-Instruct  | 27.50% | 41.00%      | 16.20% | 1.10%  | 67.86%       |
| CodeQwen1.5-7B-Chat    | 20.90% | 36.27%      | 11.37% | 2.91%  | 60.72%       |
| GLM-4                  | 22.00% | 27.80%      | 8.50%  | 5.17%  | 50.00%       |
| CodeLLaMA-13B-Instruct | 17.60% | 33.30%      | 2.10%  | 2.31%  | 39.29%       |
| CodeLLaMA-7b-Instruct  | 15.50% | 28.90%      | 1.70%  | 1.47%  | 25.00%       |
## Math Programming
| Model               | Size | GSM8k | MATH | GSM-Hard | SVAMP | TabMWP | ASDiv | MAWPS | Avg  |
| ------------------- | ---- | ----- | ---- | -------- | ----- | ------ | ----- | ----- | ---- |
| CodeShell           | 7B   | 15.8  | 8.6  | 17.3     | 35.5  | 28.2   | 44.4  | 59.8  | 29.9 |
| CodeGeex-2          | 7B   | 22.2  | 9.7  | 23.6     | 39.0  | 44.6   | 48.5  | 66.0  | 36.2 |
| StarCoder-Base      | 16B  | 23.4  | 10.3 | 23.0     | 42.4  | 45.0   | 54.9  | 81.1  | 40.0 |
| CodeLLama-Base      | 7B   | 31.2  | 12.1 | 30.2     | 54.2  | 52.9   | 59.6  | 82.6  | 46.1 |
| CodeLLama-Base      | 13B  | 43.1  | 14.4 | 40.2     | 59.2  | 60.3   | 63.6  | 85.3  | 52.3 |
| CodeLLama-Base      | 34B  | 58.2  | 21.2 | 51.8     | 70.3  | 69.8   | 70.7  | 91.8  | 62.0 |
| DeepSeek-Coder-Base | 1.3B | 14.6  | 16.8 | 14.5     | 36.7  | 30.0   | 48.2  | 62.3  | 31.9 |
| DeepSeek-Coder-Base | 6.7B | 43.2  | 19.2 | 40.3     | 58.4  | 67.9   | 67.2  | 87.0  | 54.7 |
| DeepSeek-Coder-Base | 33B  | 60.7  | 29.1 | 54.1     | 71.6  | 75.3   | 76.7  | 93.3  | 65.8 |
| Yi-Coder            | 1.5B | 25.5  | 11.4 | 27.7     | 42.4  | 36.2   | 59.3  | 75.5  | 39.7 |
| Yi-Coder            | 9B   | **68.1**  | **29.1** | **61.0**     | **77.8**  | **81.2**   | **81.0**  | **93.9**  | **70.3** |

## How to Reproduce Our Results
To ensure the fairness of our evaluation, we follow the official implementations to obtain the evaluation results for most of the benchmarks we considered, including LiveCodeBench, CRUXEval-O, CodeEditorBench, and CrossCodeEval.
For HumanEval (zero-shot, multilingual), MBPP (3-shot), and 7 math programming tasks, we follow the widely adopted [evaluation codebase](https://github.com/deepseek-ai/DeepSeek-Coder/tree/main/Evaluation) released by DeepSeek-Coder. 


If you create derivative works based on this model, please include the following attribution in your derivative works:

```This work is a derivative of [The Yi Series Model You Based On] by 01.AI, licensed under the Apache 2.0 License.```


