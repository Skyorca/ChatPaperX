
Github项目ChatPaper的改进版

原项目：https://github.com/kaixindelele/ChatPaper

motivation: 原始项目走的是arxiv检索api，检索结果存在诸多问题比如检索结果影响力较低、相关性较差等。所以替换成arxiv xplore的json接口。
它的检索相关性是gpt算出的，因此检索结果质量较高。

introduction:
本项目是two-stage: 首先通过用户指定的关键词组合检索arxiv上强相关的、具有一定影响力的论文，下载到本地；
然后通过chatpgt输出每篇论文的summary。

usage:
python chat_paperX.py  --keyword  kw1,kw2,kw3  --max_results 10

每个关键词可以为单词，通过逗号分隔。 max results是最大分析文章数。

程序执行时，会在当前执行文件夹下创建/pdf_files/{本次查询形成的文件夹名}，然后下载当前query下检索到的文章pdf，。
然后在本地export/{本次查询形成的文件夹名}文件夹下存储chatgpt返回的summary。

注意：
1. 代码里没有加代理。需要vpn开全局模式。
2. apikey.ini中填充openai key。
3. 削减了原项目的直接从本地读取pdf的功能，只提供在线下载论文pdf的一种方式