It took all we had to just keep up with the many developments, both within and outside of Language AI
我们已竭尽全力，才勉强跟上语言 AI 内外纷至沓来的诸多新进展。
# 大模型发展历史基础认识
## Bag-of-words
词袋模型（忽略语序与语法，仅统计词频的文本表示方法）
## word2vec
Word2Vec 模型（通过上下文预测或反向预测，把词转为稠密向量的浅层神经网络方法）
## recurrent neural networks (RNNs)
循环神经网络
These are variants of neural networks that can model sequences as an additional input。
这些是神经网络的变体，它们可以把“序列”当作额外输入来建模。
To do so, these RNNs are used for two tasks, encoding or representing an input sentence and decoding or generating an output sentence。
为此，循环神经网络通常要完成两个任务，把输入的文本编码/解译成向量，把向量解码/生成为文本。
Each step in this architecture is autoregressive
## attention   
注意力机制
Attention allows a model to focus on parts of the input sequence that are relevant to one another
注意力机制使模型能够聚焦于输入序列中彼此相关的部分。
### 自注意力机制里，**每个输入向量要生成 3 个向量**
- **Q (Query)**：查询向量
- **K (Key)**：键向量
- **V (Value)**：值向量
### 自注意机制的工作流程：
**步骤 1**：生成 Q、K、V 矩阵（核心）
- $W_Q$（Query 权重）
- $W_K$（Key 权重）
- $W_V$（Value 权重）
**步骤 2**：计算注意力分数（相似度）
用每个词的 Q，和所有词的 K 做**点积**（衡量相似度），再除以$(d_k)^{0.5}​​$
（$d_k$​是 K 向量的维度）
**步骤 3**：Softmax 归一化（转成权重）
把每个行的分数做 Softmax，让权重之和为 1，代表 “关注程度”：
**步骤 4**：加权求和（生成最终输出）
用每个词的注意力权重，对所有词的 $V$ 向量做加权求和，得到该词的自注意力输出。
## transform
Transform is solely based on the attention mechanism and removed the recurrence network。
Transform模型是完全基于注意力机制建立的，并且移除了循环网络。
In the Transformer, encoding and decoder components are stacked on top of each other。
在transform模型中，解码器和编码器被**层层堆叠**在一起。
Both the encoder and decoder blocks would revolve around attention instead of leveraging an RNN with attention features.
无论是编码器还是解码器模块，都将以注意力为核心，而不再使用“带注意力功能的 RNN”结构。
The encoder block in the Transformer consists of two parts, self-attention and a feedforward neural network.
transform模型中的编码模块由两部分组成，自注意力（self-attention）和前馈神经网络（feed-forward neural network）。
![[Pasted image 20251223173057.png]]
Compared to previous methods of attention, self-attention can attend to different positions within a single sequence, thereby more easily and accurately representing the input sequence. Instead of processing one token at a time, it can be used to look at the entire sequence in one go.
与以往的的注意力机制相比，自注意力可以关注到单一序列中的不同的位置。因此，他能更容易和更准确的表示输入序列。与以往的逐个token处理进程不同，它能够从整体的态度来看序列。
Compared to the encoder, the decoder has an additional layer that pays attention to the output of the encoder (to find the relevant parts of the input)
与编码器相比，解码器多出一个“交叉注意力”层，用来关注编码器的输出，从而定位输入中最相关的部分。
![[Pasted image 20251223173508.png]]
the self-attention layer in the decoder masks future positions so it only attends to earlier positions to prevent leaking information when generating the output.
在解码器中的自关注层会对未来的位置进行掩码，使得在生成输出内容时，只关注于已输入的内容，从而避免信息泄露。
![[Pasted image 20251223174237.png]]
两种模型的发展
[Representation models(Encoder-only model)](仅编码器模型.md)
[Generative models(Decoder-only model)](仅解码器模型.md)
# The Training Paradigm of Large Language Models
大语言模型的训练范式
![[Pasted image 20251224205846.png]]
