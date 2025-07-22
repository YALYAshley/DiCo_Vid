# DiCo_Vid
Diffusion-Conditioned Multi-modal Large Language Models for Video Understanding

## 📝 Change Logs
* [2025-07-22]: Create the Projects, and upload data, pre-trained LLM, ablation study links.
* [TODO] All code will be released.

## 🛠️ Requirements and Installation
Basic Dependencies:
* Python >= 3.8
* Pytorch >= 1.10.0
* CUDA Version >= 11.8
* transformers >= 4.28.0

**[Online Mode]** Install required packages (better for development):
```bash
git clone https://github.com/YALYAshley/DiCo_Vid
cd DiCo_Vid
pip install -r requirements.txt
```

**[Offline Mode]** Install DiCo_Vid as a Python package (better for direct use):
```bash
git clone https://github.com/YALYAshley/DiCo_Vid
cd DiCo_Vid
pip install --upgrade pip  
pip install -e .
```

## 📊 Datasets
We conduct experiments on eight widely used video understanding benchmark, three major tasks: video question answering (VideoQA), video captioning (VideoCap), and long-term video understanding (LTVU). [MSVD-QA](https://github.com/xudejing/video-question-answering) comprises 1,970 videos, [MSRVTT-QA](https://github.com/xudejing/video-question-answering) is a larger-scale dataset with over 10,000 videos and more diverse questions, [ActivityNet-QA](https://github.com/MILVLG/activitynet-qa) focuses on long-form, untrimmed videos with fine-grained annotations, totaling 795 videos. We follow the official training, validation, and test splits for all VideoQA datasets. [MSVD](https://github.com/xudejing/video-question-answering) and [MSRVTT](https://github.com/xudejing/video-question-answering) provide high-quality human-written captions for short. [YouCook2](http://youcook2.eecs.umich.edu/), in contrast, is composed of longer instructional cooking videos and temporally grounded captions. We follow standard splits and metrics for video captioning. [Breakfast](https://serre-lab.clps.brown.edu/resource/breakfast-actions-dataset/) comprises 1,712 videos depicting breakfast preparation scenarios, with an average length of 2.7 minutes. It focuses on fine-grained action segmentation and composite activity recognition. [COIN](https://coin-dataset.github.io/) is a large-scale instructional dataset containing 11,827 YouTube videos spanning 180 distinct tasks across 12 domains of daily life, with an average video duration of 2.36 minutes.

Suppose your data structure is like:
```bash
datasets
│   ├── MSVD
│   |   ├── frames
│   |   ├── videos
|   |   └── annoations
...
```


## 🗝️ Training & Evaluation
**[Pre-trained LLM]** 
We use the pre-trained Q-Former weights from [InstructBLIP](https://storage.googleapis.com/sfr-vision-language-research/LAVIS/models/InstructBLIP/instruct_blip_vicuna7b_trimmed.pth) and [Vicuna-7B](https://huggingface.co/lmsys/vicuna-7b-v1.5) as the LLM.

**[Training]** 
```bash
bash DiCo_Vid/scripts/${dataset_name}/train.sh
```

**[Testing]** 
```bash
bash DiCo_Vid/scripts/${dataset_name}/test.sh ${checkpoint_path}
```

**[Ablation study]** 
1) [Vicuna-7B](https://huggingface.co/lmsys/vicuna-7b-v1.5)
2) [Vicuna-13B](https://huggingface.co/lmsys/vicuna-13b-v1.5)
3) [Llama 2-7B](https://huggingface.co/meta-llama/Llama-2-7b)
4) [Mistral-7B](https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.3)



## 📑 Citation
TODO
