## Name : XXX

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
| tinyllama-1.1b-chat-v0.3.Q4_K_M.gguf | x/10     |
| TinyLlama-1.1B-Chat-v1.0-f16         | x/10     |
| TinyLlama-1.1B-Chat-v1.0-Q8          | x/10     |

### Questions

* What problems you encountered? How you solve it?
eos(--ignore-eos), apply too many layer of gpu make the prompt become meaningless/repeat same stuff(reduce the layer number)
* What you observed between CPU / GPU performance ?
* Will quantization or smaller-parameters model impact model accuracy or inference throughput ? If so , what's the variation?
