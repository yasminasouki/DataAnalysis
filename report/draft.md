# Detecting Pneumonia in Chest X-Rays: A Supervised and Unsupervised Learning Approach

> Working draft. Write each section right after finishing the matching step.
> Delete the prompts (lines starting with ">") as you fill sections in.

---

## Cover Page
- Title: (above)
- Course: Data Analysis — Project S2 2025-2026
- University: Université Antonine
- Students: Yasmina Souki, Joy
- Instructor:
- Date:

---

## Project Overview (draft — refine as needed)

Pneumonia is a lung infection that remains one of the leading causes of death worldwide, and
chest X-rays are the most common tool used to diagnose it. Reading X-rays requires trained
radiologists, who are not always available, and their interpretations can differ. This project
investigates whether machine learning can help detect pneumonia from chest X-rays. Using the
RSNA Pneumonia Detection Challenge (2018) dataset, made of adult chest X-rays from the US National
Institutes of Health annotated by radiologists into three groups (Normal, Lung Opacity, and
Not Normal without lung opacity), we apply two complementary approaches. First, a supervised
approach trains a convolutional neural network using transfer learning to classify the X-rays,
evaluated with accuracy, precision, recall, F1-score, and a confusion matrix, and interpreted
with Grad-CAM heatmaps that show which regions of the image drive each prediction. Second, an
unsupervised approach extracts image features from the network and applies PCA and K-Means
clustering without labels, then compares the discovered groups with the real classes and with
patient information such as age, sex, and how the X-ray was taken. Together, these methods
evaluate how well pneumonia can be detected automatically and whether the model learns the
disease itself or relies on shortcuts in the data.

---

## Abstract
> Write LAST. ~150–250 words: problem, dataset, methods, key results (with numbers), main conclusion.

## 1. Introduction
> Context: what pneumonia is, how it is diagnosed, role of chest X-rays, shortage of radiologists,
> promise and risks of AI in radiology. Research question. Outline of the report.

## 2. Research Background
> Aim for 4–6 sources. For each: data used, method, results, link to this project.
> Candidates: the RSNA challenge and its dataset paper; NIH ChestX-ray14 (Wang et al., 2017);
> CheXNet (Rajpurkar et al., 2017); Kermany et al. (2018, Cell); studies on shortcut learning /
> confounding in chest X-ray models (e.g. Zech et al., 2018).
> End with the gap this project addresses.

## 3. Dataset Description
> - Source: RSNA Pneumonia Detection Challenge 2018; images from the NIH Clinical Center;
>   annotations by radiologists. Terms of use and attribution.
> - Number of patients/images, image size and format (DICOM).
> - The three classes and their counts; bounding boxes exist but are not used (classification only).
> - Metadata stored in each image: age, sex, view position (PA = standing, AP = lying/bedside).
> - What the "features" are for images (pixels) and how the subset was built (size, resizing).
> - Exploratory charts: class distribution, age distribution, view position by class, example images.
> - Objective: classification and clustering of chest X-rays.

## 4. Methodology
> 4.1 Preprocessing: subset selection, resizing (e.g. 224×224), normalization, stratified
>     train/validation/test split by patient, data augmentation (if used).
> 4.2 Supervised: baseline model; CNN with transfer learning (which pretrained network, which
>     layers retrained, why); class imbalance handling; metrics and why recall matters.
> 4.3 Interpretation: Grad-CAM.
> 4.4 Unsupervised: feature extraction (embeddings), PCA, K-Means, choosing k (elbow, silhouette),
>     comparing clusters with classes and metadata.

## 5. Results & Analysis
> 5.1 Supervised: metrics table (baseline vs CNN), confusion matrix, training curves, Grad-CAM examples.
> 5.2 Shortcut test: performance by view position (AP vs PA).
> 5.3 Unsupervised: PCA plot, elbow/silhouette, cluster vs class and cluster vs metadata tables.

## 6. Discussion
> Interpret results; which classes are confused and why; does the model look at the lungs?
> Do clusters follow disease or acquisition factors? Link to research background.
> Limitations: subset size, image resolution, label noise, single data source, compute limits.
> Ethics: AI as a support tool, not a replacement for radiologists.

## 7. Conclusion
> Answer the research question directly. Key takeaways. Future work.

## References
> RSNA dataset (with required attribution), papers, libraries.
