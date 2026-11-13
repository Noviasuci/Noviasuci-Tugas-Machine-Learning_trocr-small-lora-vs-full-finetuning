# Noviasuci-Tugas-Machine-Learning_trocr-small-lora-vs-full-finetuning
Tugas penelitian ini membandingkan efisiensi parameter dan kinerja pengenalan teks pada model TrOCR Small menggunakan pendekatan Low-Rank Adaptation (LoRA) dan Full Fine-Tuning.

## Dataset

Dataset: IndoSceneTextRecognition-Synth-120K

Sumber: https://huggingface.co/datasets/abdanmulia/IndoSceneTextRecognition-Synth-120K

Penelitian menggunakan 5.000 citra sintetis dengan pembagian:
- Training: 4.000 citra
- Validation: 500 citra
- Testing: 500 citra

## Konfigurasi LoRA

- Base model: `microsoft/trocr-small-printed`
- Rank: 8
- Alpha: 16
- Dropout: 0.1
- Target modules: query dan value

## Hasil Evaluasi

| Metrik | Full Fine-Tuning | LoRA |
|---|---:|---:|
| CER | 0.346529 | 0.353025 |
| WER | 0.760584 | 0.705109 |
| Exact Match Accuracy | 22.8% | 25.0% |
| Trainable Parameters | 61,596,672 | 147,456 |

LoRA menggunakan sekitar 99,76% lebih sedikit parameter yang dilatih dibandingkan Full Fine-Tuning.

Hasil perbandingan bersifat eksploratif karena kedua checkpoint memiliki riwayat pelatihan dan konfigurasi decoding yang belum sepenuhnya setara.

## Teknologi

Python, PyTorch, Hugging Face Transformers, PEFT, dan Google Colab.

## Catatan

Notebook disediakan untuk mendokumentasikan implementasi dan analisis eksperimen. Reproduksi hasil memerlukan akses ke dataset dan checkpoint model yang sesuai.
