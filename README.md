# CS224N default final project (2022 RobustQA track)

## Starter code for robustqa track
- Download datasets from [here](https://drive.google.com/file/d/1Fv2d30hY-2niU7t61ktnMsi_HUXS6-Qx/view?usp=sharing)
- Setup environment with `conda env create -f environment.yml`
- Train a baseline MTL system with `python train.py --do-train --eval-every 2000 --run-name baseline`
- Evaluate the system on test set with `python train.py --do-eval --sub-file mtl_submission.csv --save-dir save/baseline-01`
- Upload the csv file in `save/baseline-01` to the test leaderboard. For the validation leaderboard, run `python train.py --do-eval --sub-file mtl_submission_val.csv --save-dir save/baseline-01 --eval-dir datasets/oodomain_val`


- Finetune a pretrained model with `python train.py --do-finetune --eval-every 10 --num-epochs 20 --run-name finetune`. Assume load pretrain from baseline on ID datasets and finetune on OOD datasets
- Validation leaderboard a finetuned model with `python train.py --do-eval --sub-file mtl_submission_val.csv --save-dir save/finetune-04 --eval-dir datasets/oodomain_val`


- Generate EDA Augmentation Dataset with `python3 eda.py --datasets-name race --run-name rd --alpha 0.3 --naugs 1`


