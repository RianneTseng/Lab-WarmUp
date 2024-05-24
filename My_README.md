## Name : 曾若恩

### Basic Challenge


| Throughputs (Tokens/sec)             | CPU  | GPU  |
| ------------------------------------ | ---- | ---- |
| tinyllama-1.1b-chat-v0.3.Q4_K_M.gguf | 7.72 | 143.77 |

### Medium Challenge


| Throughputs (Tokens/sec)             | CPU  | GPU  |
| ------------------------------------ | ---- | ---- |
| tinyllama-1.1b-chat-v0.3.Q4_K_M.gguf | 7.72 | 143.77 |
| TinyLlama-1.1B-Chat-v1.0-f16         | 4.19 | 23.28 |

### Advance Challenge


| Throughputs (Tokens/sec)             | CPU  | GPU  |
| ------------------------------------ | ---- | ---- |
| tinyllama-1.1b-chat-v0.3.Q4_K_M.gguf | 7.72 | 143.77 |
| TinyLlama-1.1B-Chat-v1.0-f16         | 4.19 | 23.28 |
| TinyLlama-1.1B-Chat-v1.0-Q8          | 5.78 | 16.96 |

### Advance Challenge


| Throughputs (Tokens/sec)             | Accuracy |
| ------------------------------------ | -------- |
| tinyllama-1.1b-chat-v0.3.Q4_K_M.gguf | 0/10     |
| TinyLlama-1.1B-Chat-v1.0-f16         | 8/10     |
| TinyLlama-1.1B-Chat-v1.0-Q8          | 6/10     |

### Questions

* What problems you encountered? How you solve it?
  
When I tried to infer using the converted model, I encountered an issue where the model only generated special tokens like &lt;s> and &lt;/s>, without producing any meaningful output. I couldn't find any useful information about this problem online. So, I decided to inspect the file I downloaded from Huggingface. I discovered that </s> is the end-of-stream (EOS) token, which causes the prompt to stop as soon as this token is encountered. To address this, I used the "./main -h" command to check the flag settings. Eventually, I found the "--ignore-eos" flag, which ignores the EOS token and allows the generation to continue. After adding this flag to my command, the prompt worked properly.
* What you observed between CPU / GPU performance ?
  
The GPU outperforms the CPU for the three model.
* Will quantization or smaller-parameters model impact model accuracy or inference throughput ? If so , what's the variation?
  
Yes, parameters of the model do impact model accuracy. Based on the accuracy of the three models, the f16 model generates better output. Theoretically, the performance should be F16 > Q8_0 > Q4_K_M due to the definitions of these models. 
Another important aspect is, the file size of the F16 model is four times larger than that of the Q4_K_M model. Therefore, when implementing a model, I think it's crucial to consider not only the performance but also the size and runtime of the model.
