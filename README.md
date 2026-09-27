# ENG2440 Assignment 1: pneumonia classification (RSNA)

Student ID 25011162. This is the private repository for ENG2440 (Medical Imaging & AI in Healthcare), Assignment 1. It holds a PyTorch pipeline that classifies frontal chest radiographs from the RSNA Pneumonia Detection Challenge as showing lung opacity consistent with possible pneumonia, or not.

## Contents

- `ENG2440_Assignment1/25011162_ENG2440_A1.ipynb`: the fully executed notebook, covering sections A-G and both bonus questions.
- `ENG2440_Assignment1/ai use declaration.txt`: the AI-use declaration required by section 7.
- `requirements.txt`: the package versions used.
- `outputs/`: empty. The notebook writes caches, predictions and model weights here.

**Medical images are not included.** In line with section 5, this repository contains no dataset, no CSV files and no X-ray images. In this copy of the notebook, the outputs of the nine cells that display X-rays (image panels and Grad-CAM overlays) are replaced by a short note. All tables, metrics and charts are kept. Re-running the notebook locally regenerates the X-ray figures.

## Reproducing the results

1. Download the RSNA image archive and the supporting files, as described in section 9 of the assignment, and arrange them like this:

   ```
   ENG2440_Assignment1/
     assignment1_labels.csv
     rsna_to_nih_mapping.csv
     data/images/mdai_public_project_LxR6zdR2_images_2018-08-20-184248/<study>/<series>/<SOP>.dcm
   outputs/
   ```

2. Install Python 3.13 and the packages listed in `requirements.txt`.
3. Start Jupyter in `ENG2440_Assignment1/` and run the whole notebook in order (Restart & Run All).
   - The first run builds image caches of about 2.5 GB in `outputs/`, and downloads the ImageNet ResNet-18 weights through torchvision.
   - A GPU is strongly recommended. A full run takes about 35-45 minutes on an RTX 5000 Ada.

The patient-level data split uses seed 42. The training runs use seeds 42, 43 and 44.
