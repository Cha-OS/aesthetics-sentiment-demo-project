# Introduction

# Corpus Flows Associated with Sentiment Analysis

source: `aesthetic-analysis.json`

# Corpora Flows Associated with Sentiment Analysis

Each corpora-flow consists of dedicated sections for each plain text corpus it processes. It invokes tasks from the corpus-flow necessary for each task and tweaks any relevant parameters, such as how a particular document should be parsed and split into words and sentences.

## nabokov-english

Novels written in English:

Novels Nabokov
English: corpus-en, sinister-en, lolita-en, pnin-en, harlequins-en, invite-en, gift-en, defense-en, knave-en, speak-en

Novels used in this experiment: corpus-en, lolita-en, pnin-en, speak-en

## Other books to be added in future experiments

### Nabokov’s Novels in English
1. **(1941) The Real Life of Sebastian Knight**
2. **(1947) Bend Sinister**
3. **(1955) Lolita, self-translated into Russian (1965)**
4. **(1957) Pnin**
5. (1962) Pale Fire
6. (1969) Ada or Ardor: A Family Chronicle
7. (1972) Transparent Things
8. **(1974) Look at the Harlequins!**
9. Plus **Speak, Memory (1951/1967)**

# Example Flow with possible future additions 

## import documents (corpora)

## English

## Russian
## import documents (balanced corpora)
- Brown Fiction
- Russian National Corpus (fiction)
## parse documents
## POS, both unigrams and bigrams combinations of two (we can mention we support trigrams but not necessary to use them)
## do POS-mapping
## visualizing of distributions
## Calling up examples of text with the POS bigrams and unigrams (more than X)
## Sentence length
## Richness (mention exoticism, but unnecessary to run)
## Etymology
- As a special bonus, would be great to run etymology in Russian too - was it possible?
## SoW?

# Running

**IMPORTANT ABOUT NAMING**: corpora flows are renamed to avoid collisions of namespace and NamespaceName, for example: namespace: aesthetics-sentiment-demo.data.lolita-en and NsN: aesthetics-sentiment-demo.data.lolita-en:pos

(NOTE: BukvikDatasets: setDataset > BukvikNamespaceContainer: setEntity > _getContainer >
```sh
cdbd
cd ../..
mkdir datasets
cd datasets
git clone https://github.com/Cha-OS/aesthetics-sentiment-demo-corpora
```


```sh
cdbp
```

## corpora flow

### Execute a corpora-flow

(server)

```sh
python RunBukvik.py -env ../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../experiments/projects/aesthetics-sentiment-demo-project/flows/english-sentiment.json
```

(zhenia)

```sh
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.zhenia.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/english-sentiment.json
```

### Execute a particular task (one text) of the corpora-flow:

```sh
python RunBukvik.py -env ../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../experiments/projects/aesthetics-sentiment-demo-project/flows/english-sentiment.json -cmd execTask -t "<NAMESPACE_TASK>.lolita-en"
```

(zhenia)

```
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/english-sentiment.json -cmd execTask -t "<NAMESPACE_TASK>.lolita-en"
```

(mprinc)

```sh
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.mprinc.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/english-sentiment.json
```
### Execute a task in corpora-flow:

(server)

```sh
python RunBukvik.py -env ../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../experiments/projects/aesthetics-sentiment-demo-project/flows/english-sentiment.json -cmd execTask -t "<NAMESPACE_TASK>.corpus-en"
```

(zhenia)

```
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/english-sentiment.json -cmd execTask -t "<NAMESPACE_TASK>.corpus-en"
```

(mprinc)

```sh
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.mprinc.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/english-sentiment.json -cmd execTask -t "<NAMESPACE_TASK>.corpus-en"
```

## corpus flow

### Execute whole flow:

(server)

```sh
python RunBukvik.py -env ../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json
```

(zhenia)

```
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json
```

### Execute particular task (`<NAMESPACE_TASK>.import.importing-the-corpus`):

(server)

```sh
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.execute.corpus-en"
```

(zhenia)

```
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.execute.corpus-en"
```

(mprinc)

```sh
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.mprinc.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.import.importing-the-corpus"
```

### Execute particular task (`<NAMESPACE_TASK>.parsers.words`):

(server)

```sh
python RunBukvik.py -env ../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.parsers.words"
```
(zhenia)

```
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.parsers.words"
```

(mprinc):

```sh
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.mprinc.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.parsers.words"
```

### Execute particular task (`<NAMESPACE_TASK>.pos.parsing-pos-external`):

(server)

```sh
python RunBukvik.py -env ../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.pos.parsing-pos-external"
```

(zhenia)

```
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.pos.parsing-pos-external"
```

(mprinc):

```sh
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.mprinc.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.pos.parsing-pos-external"
```

### Execute particular task (`<NAMESPACE_TASK>.pos.remapping-pos-tags`):

(server)

```sh
python RunBukvik.py -env ../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.pos.remapping-pos-tags"
```

(zhenia)

```
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.pos.remapping-pos-tags"
```

(mprinc):

```sh
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.mprinc.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.pos.remapping-pos-tags"
```

### Execute particular task (`<NAMESPACE_TASK>.pos.exporting-pos-document`):

(server)

```sh
python RunBukvik.py -env ../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.pos.exporting-pos-document"
```

(mprinc)
```sh
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.mprinc.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.pos.exporting-pos-document"
```

(zhenia)

```sh
python RunBukvik.py -env ../../../experiments/projects/aesthetics-sentiment-demo-project/environments/aesthetics-sentiment-demo.env.server.json -exp ../../../experiments/projects/aesthetics-sentiment-demo-project/flows/aesthetic-analysis.json -cmd execTask -t "<NAMESPACE_TASK>.pos.exporting-pos-document"
```
