---
language:
- ko
license: apache-2.0
library_name: keras  # Optional.
tags:
- kogpt2
- single-label-classification
datasets:
- kisti/paper-code
metrics:
- train_accuracy
- train_loss
- train_accuracy
- train_loss
- test_accuracy
- test_loss

# Optional. Add this if you want to encode your eval results in a structured way.
model-index:
- name: kogpt2-demo
  results:
  - task:
      type: sigle-label-classification             # Required.
      name: Signle Lael Classification             # Optional.
    model:
      type: pre-trained
      name: kogpt2
      args:
        n_epochs: 3
        lr: 5e-05
        batch_size: 8
    dataset:
      type: kisti/paper-code                       # Required. 
      name: Paper Classification Coce (Korean)     # Required.
      split:
        train: 0.64
        valid: 0.16
        test: 0.2
      revision: 5503434ddd753f426f4b38109466949a1217c2bb  # Optional
      args:
        input: PAPER_TEXT
        target: RCMN_CD1
        max_length: 64
    metrics:
      - type: train_accuracy
        value: 0.7933491468429565
      - type: train_loss
        value: 0.5298528075218201
      - type: test_accuracy
        value: 0.7424242496490479
      - type: test_loss
        value: 0.8049081563949585
      - type: valid_accuracy
        value: 0.6132075190544128
      - type: valid_loss
        value: 0.9963229894638062
---
