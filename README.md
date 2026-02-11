#  Korean Food Image Classification
### VGG16 Transfer Learning → Data Augmentation → Fine-Tuning

한국 음식 6종을 분류하는 이미지 분류 프로젝트 

</br>
ImageNet 사전학습 모델(VGG16)을 기반으로 Transfer Learning부터 Fine-tuning까지 전체 딥러닝 파이프라인 구현

---


## Model Architecture

Backbone:
- VGG16 (ImageNet Pretrained)

Training Pipeline:
1. Feature Extraction (Conv layers freeze)
2. Image Augmentation 적용
3. Fine-tuning (마지막 Conv block unfreeze)
4. Class imbalance 대응 (Weighted CrossEntropy)

Optimizer:
- Adam (Feature Extraction)
- SGD + Momentum (Fine-tuning)

---

## Final Performance (Validation)

| Metric | Score |
|--------|--------|
| Accuracy | 0.9376 |
| Macro F1 | 0.9353 |
| Macro Recall | 0.9383 |

---

### Project Structure

```
korean-food-classifier/
├─ training/
│   └─ jupyter-food.ipynb        # Kaggle training notebook
├─ streamlit_app/
│   ├─ food.py                   # Streamlit inference app
│   ├─ best_food_vgg16_ft.pth    # Trained model weights
│   └─ label.pkl                 # Class label mapping
└─ README.md
```

