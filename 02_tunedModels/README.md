# Fine-tuned RoBERTa Models 
This repo contains the model weights and configs of two RoBERTa models that have been fine-tuned.

## Subdir Structure 
```
02_tunedModels/
├── README.md
├── polarity_roberta
│   ├── config.json
│   ├── model.safetensors
│   └── training_args.bin
└── value_roberta
    ├── config.json
    ├── model.safetensors
    └── training_args.bin
```

## Fine-tuned Classes
The models above are trained to infer the following classes (keys). You can use this as a map to get the human label.
```
prediction_to_label_map = {
    "polarity": {
        0: "None",
        1: "(+)",
        2: "(–)",
        },
    "value": {
        0: "None",
        1: "Clarity", 
        2: "Consistency", 
        3: "Novelty", 
        4: "Thoroughness", 
        5: "Accuracy", 
        6: "Replicability", 
        }
    }
```