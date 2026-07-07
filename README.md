
## Dataset
[PlantVillage](https://www.kaggle.com/datasets/emmarex/plantdisease) on
Kaggle, filtered to tomato only (10 classes, ~16,000 images).

## Approach
- Transfer learning on MobileNetV2 (pretrained on ImageNet), base layers
  frozen
- Custom classification head: GlobalAveragePooling2D → Dense(128, relu)
  → Dropout(0.3) → Dense(10, softmax)
- 10 epochs, Adam optimizer, 80/20 train/validation split

## How to run
Open `plant_disease_detection.ipynb` in Google Colab (GPU runtime
recommended), add your own `kaggle.json` for dataset access, run all
cells.

## Limitations
Only tomato is covered. Cassava, which is far more relevant for West
African agriculture, isn't in the PlantVillage dataset — a good next
step would be finding or building a cassava-specific dataset.
