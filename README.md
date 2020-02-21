# quizmasters
**A quiz application for Web Programming course @ LTH**

#### To do:
- [x] Convert urbandict dataset to desired format:
  - [ word_id, word, up_votes, down_votes, definition, score ]
  - score column desribes "normalized" ratio between up and down votes (0 = 50% up votes, 1 = 100% up votes)
- [ ] Wrap this all up in some sexy docker build
- [ ] Create REST API to serve the data (Python/Express?)
- [ ] Create quiz application with Angular:
  - Get definition of word => fetch three similar (or just random) words for user to choose between => get score for guessing right based on up/down vote ratio


**How to handle the dataset:**

The dataset is partitioned in /dataset/output in parquet format.

`pip install pandas pyarrow`

```
from dataset import dataframe

df = dataframe('dataset/output/*/*.parquet', ['word', 'definition', 'score'])
```


**How to build angular application:**
- npm install -g @angular/cli
- npm install
- ng update
- ng serve --open
