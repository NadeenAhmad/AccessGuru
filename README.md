# AccessGuru: Leveraging LLMs to Correct Web Accessibility Violations in HTML Code
### Overview
AccessGuru is a novel system that detects web accessibility violations in HTML code and leverages Large Language Models (LLMs) to correct them. This repository contains the implementation of AccessGuru, which includes detecting accessibility issues using Axe-Playwright and applying advanced LLM-based prompt engineering techniques to correct violations based on WCAG standards.

### Repository Structure
The repository is organized as follows:

1. HTMLSamples


SampleWebPageWithAccessibilityViolations.html: An HTML file that contains several web accessibility violations. This is used to demonstrate the detection and correction processes.

SampleWebPagNOViolations.html: The same HTML file after it has been fully transformed to comply with accessibility standards (i.e., no detected violations).

2. code
This folder contains the core code for the AccessGuru system along with the Baselines used for comparison.

AccessGuruCode
  WebAccessibilityViolationCorrection

    OUR_MetaCognitivePrompting.ipynb: A Jupyter notebook implementing the metacognitive and role-play prompting strategies to correct web accessibility violations. The notebook uses a pre-trained LLM (e.g., GPT-4, Mistral_7B) to generate corrections for detected violations.

  WebAccessibilityViolationsDetection

    ExtractWebAccessibilityViolationsUsingPlaywrightAPI.ipynb: A Jupyter notebook that uses the Playwright API integrated with the Axe tool to automatically detect web accessibility violations in HTML code. It outputs a report detailing the violations detected and assigns a violation score for each detected violation.
    
Baselines_Implementation_GPT_4o.ipynb: This notebook implements baseline methods using GPT-4 for comparison with AccessGuru. It shows the performance of standard contextual prompting techniques without the advanced corrections offered by the AccessGuru pipeline.

Baselines_Implementation_Mistral_7B.ipynb: This notebook implements baseline methods using the Mistral-7B model. Like the GPT-4 baseline, it serves as a comparison point for evaluating AccessGuru’s advanced prompting techniques.

3. data
This folder contains datasets and related files used for evaluation and benchmarking.

Baseline2Dataset.csv: Dataset from [1] containing web pages with accessibility violations used for evaluating our method AccessGuru against the baseline models.
HelpForBaselineOne.json: JSON file with help data or additional metadata related to the [].
HelpForBaselineTwo.json: JSON file containing metadata or help data for the second baseline dataset.
OurDataset.csv: A novel dataset collected specifically for this project, containing web pages with a range of accessibility violations for testing AccessGuru’s correction capabilities.
WCAGGuidelines.csv: A dataset that includes the relevant Web Content Accessibility Guidelines (WCAG) standards. This file provides detailed guidelines to ensure that the corrections generated by the system are compliant.
4. README.md
The file you are currently reading. It provides an overview of the repository, explains the folder structure, and highlights the key components of AccessGuru.

### How to Use
Running the Detection Pipeline
Open the ExtractWebAccessibilityViolationsUsingPlaywrightAPI.ipynb notebook in your preferred Jupyter environment.
Run the cells to load the HTML sample file and execute the Axe-Playwright tool to detect accessibility violations.
Review the generated report of violations in the output.

Running the Correction Pipeline
Open the OUR_MetaCognitivePrompting.ipynb notebook.
Input the detected violations and run the notebook to generate LLM-based corrections.
Review the corrected HTML and assess its compliance with accessibility guidelines.

Comparing Baselines
To compare the AccessGuru approach with standard techniques, run the Baselines_Implementation_GPT_4o.ipynb and Baselines_Implementation_Mistral_7B.ipynb notebooks. These implement baseline models for detecting and correcting accessibility violations.

### References

[1] Re-Act Prompting: Calista Huang, Alyssa Ma, Suchir Vyasamudri, Eugenie Puype, Sayem Kamal, Juan Belza Garcia, Salar Cheema, and Michael Lutz. 2024. ACCESS: Prompt Engineering for Automated Web Accessibility Violation Corrections. CoRR abs/2401.16450 (2024). https://doi.org/10.48550/ARXIV.2401.16450 arXiv:2401.16450

[2] Contextual Prompting: Achraf Othman, Amira Dhouib, and Aljazi Nasser Al Jabor. 2023. Fostering websites accessibility: A case study on the use of the Large Language Models ChatGPT for automatic remediation. In Proceedings of the 16th International Conference on PErvasive Technologies Related to Assistive Environments, PETRA 2023, Corfu, Greece, July 5-7, 2023. ACM, 707–713. https://doi.org/10.1145/3594806.3596542


[3] Zero-shot Prompting: Giovanni Delnevo, Manuel Andruccioli, and Silvia Mirri. 2024. On the Interaction with Large Language Models for Web Accessibility: Implications and Challenges. In 21st IEEE Consumer Communications & Networking Conference, CCNC 2024, Las Vegas, NV, USA, January 6-9, 2024. IEEE, 1–6. https://doi.org/10.1109/CCNC51664.2024.10454680
