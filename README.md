# GeoILP: A Synthetic Dataset to Guide Large-Scale Rule Induction



This repository contains the dataset **GeoILP**, corresponding to our ICLR 2025 paper [GeoILP: A Synthetic Dataset to Guide Large-Scale Rule Induction](https://openreview.net/forum?id=cfGpIcOIa5).



Each json file contains one Inductive Logic Programming task. The mock task below explains content structure.
```json5
{
    "meta_data": {
        "is_multitask": true,  // `true` for multi-task, `false` for single-task
        "target_predicates": [  // target predicates
            "circle",
            "cong",
        ]
    },
    "data": {
        "train": {
            "background_knowledge": [  // background knowledge (for training)
                "eqangle(A0, C0, B0, C0, A0, C0, B0, C0)",
            ],
            "positive_examples": [  // positive examples (for training)
                "cong(G0, D0, G0, F0)",
            ],
            "proof_steps": [  // proof steps of positive examples given background knowledge, i.e., ground rules for forward chaining (for training)
                {
                    "body": [  // body atoms of a Horn rule
                        "cong(G0, E0, G0, F0)",
                        "cong(G0, D0, G0, E0)"
                    ],
                    "head": "cong(G0, D0, G0, F0)"  // head atoms of a Horn rule
                }
            ]
        },
        "eval": {
            "background_knowledge": [  // background knowledge (for evaluation)
                "eqangle(A1, C1, B1, C1, A1, C1, B1, C1)",
            ],
            "positive_examples": [  // positive examples (for evaluation)
                "cong(G1, D1, G1, F1)",
            ],
            "proof_steps": [  // proof steps (ground rules) of positive examples given background knowledge, i.e., ground rules for forward chaining (for evaluation)
                {
                    "body": [
                        "cong(G1, E1, G1, F1)",
                        "cong(G1, D1, G1, E1)"
                    ],
                    "head": "cong(G1, D1, G1, F1)"
                }
            ]
        }
    } 
}
```

Please consult our paper for more details.



## TODO

Release image-form data.
