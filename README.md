# MCQFormatBench

This respository contains the dataset for MCQFormatBench, a benchmark for evaluating the robustness of LLMs against format changes in multiple-choice questions.

This work is based on our paper: [MCQFormatBench: Robustness Tests for Multiple-Choice Questions](https://aclanthology.org/2025.gem-1.69/), accepted at the [GEM<sup>2</sup> Workshop 2025](https://gem-benchmark.com/workshop) (ACL 2025).

## Abstract

Multiple-choice questions (MCQs) are often used to evaluate large language models (LLMs). They measure LLMs’ general common sense and reasoning abilities, as well as their knowledge in specific domains such as law and medicine. However, the robustness of LLMs to various question formats in MCQs has not been thoroughly evaluated. While there are studies on the sensitivity of LLMs to input variations, research into their responsiveness to different question formats is still limited. In this study, we propose a method to construct tasks to comprehensively evaluate the robustness against format changes of MCQs by decomposing the answering process into several steps. Using this dataset, we evaluate nine LLMs, such as Llama3-70B and Mixtral-8x7B. We find the lack of robustness to differences in the format of MCQs. It is crucial to consider whether the format of MCQs influences their evaluation scores when assessing LLMs using MCQ datasets.

## Data Field

- **id**: Sequential instance identifier (0-based)
- **process**: Cognitive process being tested
  - `"Recognize Input"`
  - `"Understand Question"`
  - `"Select Answer"`
  - `"Generate Answer"`
- **task**: Specific task type
  - `"Remember Question"`
  - `"Remember Options"`
  - `"Format Change"`
  - `"Option Modification"`
  - `"Negation"`
  - `"Faithful Selection"`
  - `"Specify Format"`
  - `"Default"`
- **sub_task**: Task subtype (when applicable)
- **prompt**: Full input prompt for the model
- **question**: Original question text (for `Remember Question` task)
- **options**: List of 4 answer choices
- **correct_answer_index**: Index of correct answer (0-3) or list for multi-correct tasks
- **choice**: Answer choice type (`"content"` or `"label"`)
- **output_format**: Expected output format (`"content"`, `"label"`, or `"both"`) (for `Specify Format` task)
- **format**: Current question format (`"SimpleQ"`, `"Continuation"`, `"GapFill"`)
- **original_format**: Source format (for `Format Change` task)

## Citation
If you use this dataset in your research, please cite our paper:

```
@inproceedings{takizawa-etal-2025-mcqformatbench,
    title = "{MCQF}ormat{B}ench: Robustness Tests for Multiple-Choice Questions",
    author = "Takizawa, Hiroo  and
      Sugawara, Saku  and
      Aizawa, Akiko",
    booktitle = "Proceedings of the Fourth Workshop on Generation, Evaluation and Metrics (GEM{\texttwosuperior})",
    month = jul,
    year = "2025",
    address = "Vienna, Austria and virtual meeting",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2025.gem-1.69/",
    pages = "824--846"
}
```

## License

This dataset is released under the MIT License. See the LICENSE file for more details.

## Acknowledgment

This dataset is built upon the MMLU dataset.

- MMLU (Massive Multitask Language Understanding)
  - Copyright (c) 2020 Dan Hendrycks
  - Licensed under the MIT license.
