<div class="Box-sc-g0xbh4-0 bJMeLZ js-snippet-clipboard-copy-unpositioned" data-hpc="true"><article class="markdown-body entry-content container-lg" itemprop="text"><div class="markdown-heading" dir="auto"><h1 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用 GPT-4 进行指令调整</font></font></h1><a id="user-content-instruction-tuning-with-gpt-4" class="anchor" aria-label="永久链接：使用 GPT-4 进行指令调整" href="#instruction-tuning-with-gpt-4"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">彭宝林*、李春元*、何鹏程*、Michel Galley、高剑峰（*同等贡献）</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">[</font></font><a href="https://instruction-tuning-with-gpt-4.github.io/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">项目页面</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">] [</font></font><a href="https://arxiv.org/abs/2304.03277" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">论文</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">]</font></font></p>
<p align="center" dir="auto">
    <a target="_blank" rel="noopener noreferrer nofollow" href="https://camo.githubusercontent.com/8a358ecd5bbb5e88fc410a11303f80a1477ff2dc69f7ebdf85977044c0a541c0/68747470733a2f2f696e737472756374696f6e2d74756e696e672d776974682d6770742d342e6769746875622e696f2f696d616765732f677074346c6c616d615f6c6f676f2e706e67"><img src="https://camo.githubusercontent.com/8a358ecd5bbb5e88fc410a11303f80a1477ff2dc69f7ebdf85977044c0a541c0/68747470733a2f2f696e737472756374696f6e2d74756e696e672d776974682d6770742d342e6769746875622e696f2f696d616765732f677074346c6c616d615f6c6f676f2e706e67" width="50%" data-canonical-src="https://instruction-tuning-with-gpt-4.github.io/images/gpt4llama_logo.png" style="max-width: 100%;"></a> <br><font style="vertical-align: inherit;"><a href="https://gligen.github.io/" rel="nofollow"><font style="vertical-align: inherit;">发音为“GPT-4-LLM”或“GPT-for-LLM”，图像由GLIGEN</font></a><font style="vertical-align: inherit;">
    生成</font></font><a href="https://gligen.github.io/" rel="nofollow"><font style="vertical-align: inherit;"></font></a>
</p>
<p dir="auto"><a href="https://github.com/tatsu-lab/stanford_alpaca/blob/main/LICENSE"><img src="https://camo.githubusercontent.com/ff42248868bc1387751598955e573b397851d947f13ddd7618c0ba9e66aacdf6/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f436f64652532304c6963656e73652d4170616368655f322e302d677265656e2e737667" alt="代码许可" data-canonical-src="https://img.shields.io/badge/Code%20License-Apache_2.0-green.svg" style="max-width: 100%;"></a>
<a href="https://github.com/tatsu-lab/stanford_alpaca/blob/main/DATA_LICENSE"><img src="https://camo.githubusercontent.com/a4a284ac441fe44d95ebdfa5a60bcb41abd377726cfa5ab937f79f635bc3d57a/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f446174612532304c6963656e73652d434325323042792532304e43253230342e302d7265642e737667" alt="数据许可" data-canonical-src="https://img.shields.io/badge/Data%20License-CC%20By%20NC%204.0-red.svg" style="max-width: 100%;"></a></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">这是 GPT-4-LLM 的存储库，旨在共享 GPT-4 生成的数据，以构建具有监督学习和强化学习的遵循指令的 LLM。该仓库包含：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">GPT-4 使用 Alpaca 生成的英语指令跟踪</font></font><a href="#data-release"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">数据</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">提示微调 LLM。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">GPT-4 使用 ChatGPT 从 Alpaca 翻译而来的中文提示生成</font><font style="vertical-align: inherit;">中文指令跟踪</font></font><a href="#data-release"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">数据。</font></font></a><font style="vertical-align: inherit;"></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">按 GPT-4 排序的比较</font></font><a href="#data-release"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">数据</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，用于训练奖励模型。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">来自 GPT-4的非自然指令</font></font><a href="#data-release"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">数据</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">的答案，用于大规模量化 GPT-4 和指令调整模型之间的差距。</font></font></li>
</ul>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用和许可声明</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：数据仅供研究使用并获得许可。该数据集为 CC BY NC 4.0（仅允许非商业用途），使用该数据集训练的模型不应在研究目的之外使用。</font></font></p>
<ul dir="auto">
<li><a href="#overview"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">概述</font></font></a></li>
<li><a href="#data-release"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">GPT-4数据发布</font></font></a></li>
<li><a href="#how-good-is-the-data"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">数据有多好？</font></font></a></li>
<li><a href="#fine-tuning-with-the-data"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">根据数据进行微调</font></font></a></li>
<li><a href="#collect-results-and-reproduce-figure-plots"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">重现图形图</font></font></a></li>
</ul>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">🔥 新闻</font></font></h2><a id="user-content-fire-news" class="anchor" aria-label="永久链接：：fire：新闻" href="#fire-news"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>

<ul dir="auto">
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">[2023.04.17]</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> GPT-4可视化指令调优发布！请查看多模态模型LLaVA：[</font></font><a href="https://llava-vl.github.io/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">项目页面</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">][</font></font><a href="https://arxiv.org/abs/2304.08485" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">论文</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">][</font></font><a href="https://llava.hliu.cc/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">演示</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">] </font></font><a href="https://github.com/haotian-liu/LLaVA"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">[代码]</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">   [</font></font><a href="https://huggingface.co/datasets/liuhaotian/LLaVA-Instruct-150K" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">数据</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">][</font></font><a href="https://huggingface.co/liuhaotian/LLaVA-13b-delta-v0" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">模型</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">]</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">[2023.04.15]</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">更新了对比数据，包括三个模型响应和GPT-4评估分数。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">[2023.04.06]</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">论文和数据发布。</font></font></li>
</ul>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">概述</font></font></h2><a id="user-content-overview" class="anchor" aria-label="永久链接：概述" href="#overview"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">大型语言模型 (LLM) 已显示出令人印象深刻的泛化能力，例如上下文学习和思想链推理。为了使法学硕士能够遵循自然语言指令并完成现实世界的任务，研究人员一直在探索法学硕士的指令调整方法。为了推进 LLM 指令调优的最新技术，我们首次尝试使用 GPT-4 来生成用于 LLM 微调的指令跟踪数据。</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">数据发布</font></font></h2><a id="user-content-data-release" class="anchor" aria-label="永久链接：数据发布" href="#data-release"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<ul dir="auto">
<li>
<p dir="auto"><a href="/Instruction-Tuning-with-GPT-4/GPT-4-LLM/blob/main/data/alpaca_gpt4_data.json"><code>alpaca_gpt4_data.json</code></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">包含由 GPT-4 生成的 52K 指令跟随数据，并带有 Alpaca 提示。该 JSON 文件与 Alpaca 数据具有相同的格式，只不过输出是由 GPT-4 生成的：</font></font></p>
<ul dir="auto">
<li><code>instruction</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: </font></font><code>str</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，描述模型应执行的任务。每条 52K 指令都是唯一的。</font></font></li>
<li><code>input</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: </font></font><code>str</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，任务的可选上下文或输入。</font></font></li>
<li><code>output</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: </font></font><code>str</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，指令的答案由 生成</font></font><code>GPT-4</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></li>
</ul>
</li>
<li>
<p dir="auto"><a href="/Instruction-Tuning-with-GPT-4/GPT-4-LLM/blob/main/data/alpaca_gpt4_data_zh.json"><code>alpaca_gpt4_data_zh.json</code></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">包含由 GPT-4 生成的 52K 指令跟踪数据，并由 ChatGPT 翻译成中文的 Alpaca 提示。此 JSON 文件具有相同的格式。</font></font></p>
</li>
<li>
<p dir="auto"><a href="/Instruction-Tuning-with-GPT-4/GPT-4-LLM/blob/main/data/comparison_data_v2.json"><code>comparison_data.json</code></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">通过要求 GPT-4 评估质量，对 GPT-4、GPT-3.5 和 OPT-IML 等三种模型的响应进行排名。</font></font></p>
<ul dir="auto">
<li><code>user_input</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: </font></font><code>str</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，用于查询 LLM 的提示。</font></font></li>
<li><code>completion_a</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: </font></font><code>str</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，一个模型完成，其排名高于completion_b。</font></font></li>
<li><code>completion_b</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">: </font></font><code>str</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，不同的模型完成，其质量得分较低。</font></font></li>
</ul>
</li>
<li>
<p dir="auto"><a href="/Instruction-Tuning-with-GPT-4/GPT-4-LLM/blob/main/data/unnatural_instruction_gpt4_data.json"><code>unnatural_instruction_gpt4_data.json</code></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">包含由 GPT-4 生成的 9K 指令跟随数据，并带有非自然指令中的提示。此 JSON 文件与 Alpaca 数据具有相同的格式。</font></font></p>
</li>
</ul>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">数据有多好</font></font></h2><a id="user-content-how-good-is-the-data" class="anchor" aria-label="永久链接：数据有多好" href="#how-good-is-the-data"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"></font><a href="https://arxiv.org/abs/2112.00861" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用 Amazon Mechanical Turk 遵循Anthropic AI</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">的有益、诚实和无害标准对模型生成结果进行人工评估</font><font style="vertical-align: inherit;">。结果总结如下：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">比较了两种指令调整的 LLaMA 模型，分别根据 GPT-4 和 GPT-3 生成的数据进行微调。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在“有用性”标准中，LLaMA-GPT-4 的表现明显优于 LLaMA-GPT-3。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">LLaMA-GPT-4 在所有三个标准中的表现与原始 GPT-4 相似，这为开发最先进的遵循指令的 LLM 提供了一个有希望的方向。</font></font></li>
</ul>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="/Instruction-Tuning-with-GPT-4/GPT-4-LLM/blob/main/static/pie_llama_gpt3_vs_llam_gpt4.png"><img src="/Instruction-Tuning-with-GPT-4/GPT-4-LLM/raw/main/static/pie_llama_gpt3_vs_llam_gpt4.png" alt="LLaMA-GPT4 与羊驼毛（即 LLaMA-GPT3）" style="max-width: 100%;"></a>
<a target="_blank" rel="noopener noreferrer" href="/Instruction-Tuning-with-GPT-4/GPT-4-LLM/blob/main/static/pie_llama_gpt4_vs_gpt4.png"><img src="/Instruction-Tuning-with-GPT-4/GPT-4-LLM/raw/main/static/pie_llama_gpt4_vs_gpt4.png" alt="LLaMA-GPT4 与 GPT-4" style="max-width: 100%;"></a></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">根据数据进行微调</font></font></h2><a id="user-content-fine-tuning-with-the-data" class="anchor" aria-label="永久链接：根据数据进行微调" href="#fine-tuning-with-the-data"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">我们遵循相同的规则，使用标准 Hugging Face 训练代码将 LLaMA 微调为 Alpaca。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要使用 LLaMA 7B 重现我们的结果，首先设置 Alpaca 存储库并运行以下 CMD：</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre><span class="pl-c"><span class="pl-c">#</span># cmd we used to train LLaMA on 16*V100</span>
torchrun --nproc_per_node=16 
--master_port=12345 train.py 
--model_name_or_path PATH/TO/LLaMA
--data_path ./data/alpaca_gpt4_data.json 
--output_dir PATH/TO/SAVE
--num_train_epochs 3 
--per_device_train_batch_size 1 
--per_device_eval_batch_size 1 
--gradient_accumulation_steps 4 
--evaluation_strategy <span class="pl-s"><span class="pl-pds">"</span>no<span class="pl-pds">"</span></span> 
--save_strategy <span class="pl-s"><span class="pl-pds">"</span>steps<span class="pl-pds">"</span></span> 
--save_steps 200 
--save_total_limit 1 
--learning_rate 2e-5 
--weight_decay 0. 
--warmup_ratio 0.03 
--lr_scheduler_type <span class="pl-s"><span class="pl-pds">"</span>cosine<span class="pl-pds">"</span></span> 
--logging_steps 1 
--deepspeed configs/ds_config.json</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="## cmd we used to train LLaMA on 16*V100
torchrun --nproc_per_node=16 
--master_port=12345 train.py 
--model_name_or_path PATH/TO/LLaMA
--data_path ./data/alpaca_gpt4_data.json 
--output_dir PATH/TO/SAVE
--num_train_epochs 3 
--per_device_train_batch_size 1 
--per_device_eval_batch_size 1 
--gradient_accumulation_steps 4 
--evaluation_strategy &quot;no&quot; 
--save_strategy &quot;steps&quot; 
--save_steps 200 
--save_total_limit 1 
--learning_rate 2e-5 
--weight_decay 0. 
--warmup_ratio 0.03 
--lr_scheduler_type &quot;cosine&quot; 
--logging_steps 1 
--deepspeed configs/ds_config.json" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">为了评估结果，我们强烈建议用户参考</font></font><a href="https://vicuna.lmsys.org/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Vicuna</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，因为他们提供了很棒的服务脚本和评估管道。</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">收集结果并重现图形图</font></font></h2><a id="user-content-collect-results-and-reproduce-figure-plots" class="anchor" aria-label="永久链接：收集结果并重现图形图" href="#collect-results-and-reproduce-figure-plots"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可以使用附带的 IPython 笔记本plots/main_plots.ipynb 绘制结果。启动 IPython Notebook 服务器：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>$ cd plots
$ ipython notebook
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="$ cd plots
$ ipython notebook" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">选择</font></font><a href="/Instruction-Tuning-with-GPT-4/GPT-4-LLM/blob/main/plots/main_plots.ipynb"><code>main_plots.ipynb</code></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">笔记本并执行包含的代码。请注意，在没有修改的情况下，我们已将提取的结果复制到笔记本中，脚本将在论文中输出数字。</font></font><a href="/Instruction-Tuning-with-GPT-4/GPT-4-LLM/blob/main/plots/data"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">data</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中提供了绘图的一些相关数据</font><font style="vertical-align: inherit;">，生成的绘图保存在</font></font><a href="/Instruction-Tuning-with-GPT-4/GPT-4-LLM/blob/main/plots/output"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">plots/output</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中。如果您运行自己的训练并希望绘制结果，则必须以相同的格式组织结果。</font></font></p>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">快捷方式：要跳过所有工作并仅查看结果，请查看此带有</font></font><a href="/Instruction-Tuning-with-GPT-4/GPT-4-LLM/blob/main/plots/main_plots.ipynb"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">缓存绘图的</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">笔记本。</font></font></em></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">引文</font></font></h2><a id="user-content-citation" class="anchor" aria-label="永久链接：引文" href="#citation"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>@article{peng2023instruction,
  title={Instruction Tuning with GPT-4},
  author={Peng, Baolin and Li, Chunyuan and He, Pengcheng and Galley, Michel and Gao, Jianfeng},
  journal={arXiv preprint arXiv:2304.03277},
  year={2023}
}
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="@article{peng2023instruction,
  title={Instruction Tuning with GPT-4},
  author={Peng, Baolin and Li, Chunyuan and He, Pengcheng and Galley, Michel and Gao, Jianfeng},
  journal={arXiv preprint arXiv:2304.03277},
  year={2023}
}" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">相关项目</font></font></h2><a id="user-content-related-projects" class="anchor" aria-label="永久链接：相关项目" href="#related-projects"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<ul dir="auto">
<li><a href="https://llava-vl.github.io/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">LLaVA：使用 GPT-4 进行视觉指令调整</font></font></a></li>
<li><a href="https://github.com/microsoft/LLaVA-Med"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">LLaVA-Med：一天内培训生物医学大型语言和视觉助理</font></font></a></li>
<li><a href="https://github.com/Luodian/Otter"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Otter：具有上下文指令调整的多模态模型</font></font></a></li>
</ul>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">致谢</font></font></h2><a id="user-content-acknowledgement" class="anchor" aria-label="永久链接：致谢" href="#acknowledgement"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该存储库受益于</font></font><a href="https://github.com/facebookresearch/llama"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">LLaMA</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><a href="https://github.com/tatsu-lab/stanford_alpaca"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Alpaca</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><a href="https://github.com/lm-sys/FastChat"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Vicuna</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。感谢他们的精彩作品。</font></font></p>
</article></div>
