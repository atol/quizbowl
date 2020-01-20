# Quizbowl

Question answering task based on the QANTA (Question Answering Is Not a Trivial Activity) dataset.

## Background

Quizbowl is a trivia competition that tests knowledge and intelligence. A Quizbowl question contains multiple sentences
with clues arranged by difficulty: obscure clues appear at the beginning and obvious clues appear at the end.

Players try to answer the question correctly using the least amount of information -- questions can be interrupted as soon
as a player knows the answer.

## Getting Started

Set up the virtual environment:

```
python3 -m venv venv
source venv/bin/activate
pip3 install -r requirements.txt
```

If the virtual environment is already set up, launch it:

`source venv/bin/activate`

## Dataset

Add execute permissions to the `dataset.py` file:

`chmod u+x dataset.py`

Then run the following command to download the QANTA dataset to the `data` folder:

`./dataset.py download`

### File Descriptions

* `qanta.mapped.2018.04.18.json`: The processed dataset with Wikipedia pages matched to the answer where possible. This
includes all questions, even those without matched pages.
* `qanta.2018.04.18.sqlite3`: Equivalent to `qanta.mapped.2018.04.18.json` but in sqlite3 format
* `qanta.train.2018.04.18.json`: Training data which is the mapped dataset filtered down to only questions with non-null
page matches
* `qanta.dev.2018.04.18.json`: Dev data which is the mapped dataset filtered down to only questions with non-null
page matches
* `qanta.test.2018.04.18.json`: Test data which is the mapped dataset filtered down to only questions with non-null
page matches

## Baseline

The QANTA framework for playing Quizbowl divides the task into two subsystems: guessing and buzzing. Guessing involves
deciding *what* to answer and buzzing involves deciding *when* to answer.

The baseline system trains a TF-IDF model as the guesser and uses a threshold model as the buzzer.

## Approach

This project focuses on the guessing task for playing Quizbowl and aims to improve over the baseline accuracy.

## References

[1] [Quizbowl: The Case for Incremental Question Answering](https://arxiv.org/abs/1904.04792)

[2] [QUANTA Project](https://sites.google.com/view/qanta/resources)

[3] [QANTA Leaderboard](https://pinafore.github.io/qanta-leaderboard/)

[4] [QANTA Competition: Baseline System](https://github.com/Pinafore/qanta-codalab)
