# Get started

## Installation

Setup the library from Pypi using the following command in your terminal or command prompt.

```shell
pip install openodia
```

## Features

The tools are available in Odia language.

- [x] [Odia Alphabets](#odia-alphabets)
- [x] [Generate random Odia names](#odia-names)
- [x] [Detect Odia Language](#detect-odia-language)
- [x] [Word Tokenizer](#word-tokenizer)
- [x] [Remove stopwords](#remove-stopwords)
- [x] [Google Translate](#translation)
- [x] [Automatic extractive text summarization](#automatic-extractive-text-summarization)
- [x] [Add Dictionary corpus](#offline-dictionary)
- [ ] Add English-Odia Parallel corpus
- [ ] Add Odia Monolingual corpus
- [ ] Add NER dataset of places, actors, etc. 
- [ ] Robust paragraph to sentence tokenizer covering edge cases
- [ ] Stemming tool
- [ ] Customized stopword support
- [ ] Add OdiaBert
- [ ] Improve the CI/CD pipeline

### :material-format-letter-case: Odia alphabets 

- To get the Odia alphabets use the `alphabet` module

``` python
>>> from openodia import alphabet
>>> alphabet.all_letters
['ଁ', 'ଂ', 'ଃ', 'ଅ', 'ଆ', 'ଇ', 'ଈ', 'ଉ', 'ଊ', 'ଋ', 'ଌ', 'ଏ', 'ଐ', 'ଓ', 'ଔ', 'କ', 'ଖ', 'ଗ', 'ଘ', 'ଙ', 'ଚ', 'ଛ', 'ଜ', 'ଝ', 'ଞ', 'ଟ', 'ଠ', 'ଡ', 'ଢ', 'ଣ', 'ତ', 'ଥ', 'ଦ', 'ଧ', 'ନ', 'ପ', 'ଫ', 'ବ', 'ଭ', 'ମ', 'ଯ', 'ର', 'ଲ', 'ଳ', 'ଵ', 'ଶ', 'ଷ', 'ସ', 'ହ', '଼', 'ଽ', 'ା', 'ି', 'ୀ', 'ୁ', 'ୂ', 'ୃ', 'ୄ', 'େ', 'ୈ', 'ୋ', 'ୌ', '୍', 'ୖ', 'ୗ', 'ଡ଼', 'ଢ଼', 'ୟ', 'ୠ', 'ୡ', 'ୢ', 'ୣ', '୦', '୧', '୨', '୩', '୪', '୫', '୬', '୭', '୮', '୯', '୰', 'ୱ', '୲']
>>> alphabet.consonants
['କ', 'ଖ', 'ଗ', 'ଘ', 'ଙ', 'ଚ', 'ଛ', 'ଜ', 'ଝ', 'ଞ', 'ଟ', 'ଠ', 'ଡ', 'ଢ', 'ଣ', 'ତ', 'ଥ', 'ଦ', 'ଧ', 'ନ', 'ପ', 'ଫ', 'ବ', 'ଭ', 'ମ', 'ଯ', 'ର', 'ଲ', 'ଳ', 'ଵ', 'ଶ', 'ଷ', 'ସ', 'ହ']
>>> alphabet.vowels
['ଅ', 'ଆ', 'ଇ', 'ଈ', 'ଉ', 'ଊ', 'ଋ', 'ଌ', 'ଏ', 'ଐ', 'ଓ', 'ଔ']
>>> alphabet.numbers
['୦', '୧', '୨', '୩', '୪', '୫', '୬', '୭', '୮', '୯']
>>> alphabet.matra
['ଁ', 'ଂ', 'ଃ', '଼', 'ଽ', 'ା', 'ି', 'ୀ', 'ୁ', 'ୂ', 'ୃ', 'ୄ', 'େ', 'ୈ', 'ୋ', 'ୌ', '୍', 'ୖ', 'ୗ', '୰', 'ୱ', '୲']
```

### :people_holding_hands_tone1: Odia names

- You can generate Odia names using the `name` module with the following syntax:

``` python
>>> from openodia import name
>>> name.generate_names()
['ଯଦୁମଣୀ ମାଢ଼ୀ', 'ବାସନ୍ତି ବ୍ରହ୍ମା', 'ପ୍ରବୀଣ ସିଂହ ମୁକ୍କିମ', 'ବୃନ୍ଦାବନ ଧଳ', 'ଅଶ୍ୱିନୀ କିଶୋର ଜଗଦେବ', 'ଶ୍ରୀଯୁକ୍ତ ଇରାଶିଷ ସେଠୀ', 'କୁମାରୀ ସୁମନ ସିଂଦେଓ', 'ସଲିଲ ଅଲ୍ଲୀ ଛତ୍ରିଆ', 'ଦିବାକରନାଥ ରାଧାରାଣୀ ଆଚାର୍ଯ୍ୟ', 'ଦୁର୍ଗା ସୁନ୍ଦରସୁର୍ଯ୍ୟା ପୁଟୀ']
```
- By default it will return ten randomly generated names. 
- If you want, you can generate more names by providing the number of names needed in the first argument.

``` python
>>> name.generate_names(20)
['ସାବିତ୍ରୀ ଧଳ', 'ଶ୍ରୀଯୁକ୍ତ ଉତ୍କଳ ପାଳ', 'ଯଦୁମଣି ସୁବାହୁ', 'ପ୍ରେମଲତା ପମ', 'ଗୁରୁ ପୃଷ୍ଟି', 'ଗୀତା ଦାସବର୍ମା', 'କୁମାରୀ ଦୁର୍ଗା ବ୍ରହ୍ମା', 'କୁମାରୀ ପୁପୁଲ ହେମ୍ବ୍ରମ', 'ମକର ସାଇ', 'ଲକ୍ଷ୍ମୀକାନ୍ତ ନନ୍ଦି', 'ଶ୍ରୀ ଦୀନବନ୍ଧୁ ଲୋକ', 'କୁମାରୀ ଜିନା ଗଜପତି', 'ମୃଣାଳ ଭୂଷଣ ଛତ୍ରିଆ', 'ସୁଧାଂଶୁମାଳିନୀ ସିଂହ ସାଲୁଜା', 'ସୁଧାଂଶୁମାଳିନୀ ମହାନନ୍ଦ', 'ସୁମନୀ ନାଥ', 'କୁମାରୀ ନୀତୁ ହିକ୍କା', 'ଶ୍ରୀମତୀ ଲୀଳା କାଡାମ୍', 'ସନାତନ କୁଅଁର', 'କୁମାରୀ କବି ଦାସନାୟକ']
```
- In addition to this, you can create specific name parts like prefix, first name, middle name, surname, etc.
- By default you will get ten names. However, to get more number of results you can specify the number of names in the first argument.

``` python
>>> from openodia import name
>>> name.generate_firstnames()
['ଅନିରୁଦ୍ଧ', 'ଦେବରାଜ', 'ଆଶ୍ରିତ', 'ବଦ୍ରି', 'ସଦାଶିବ', 'ପ୍ରଦିପ୍ତ', 'ଧୃବ', 'ଶ୍ରୀନାଥ', 'ସ୍ନିତି', 'ପ୍ରକୃତି']
>>> name.generate_prefixes()
['ଶ୍ରୀଯୁକ୍ତ', 'ଶ୍ରୀମତୀ', 'କୁମାରୀ', 'ଶ୍ରୀମାନ', 'ସୁଶ୍ରୀ', 'ଶ୍ରୀ']
>>> name.generate_middlenames()
['ଲେଖା', 'ଶ୍ରୀ', 'ମାଧବ', 'କେତନ', 'ଯୋଶେଫ୍', 'କେଶରୀ', 'ଭୂଷଣ', 'ରାଧାରାଣୀ', 'ମାନସିଂହ', 'କିଶୋର']
>>> name.generate_surnames()
['ପରିଜା', 'ରଣସିଂହ', 'ମହାପାତ୍ର', 'ରଥ', 'ମହନ୍ତ', 'ବେହେରା', 'ଦେଓ', 'ଧଳ', 'ଦିଆନ', 'ହିମିରିକା']
```

### :material-text-box-search-outline: Detect Odia Language

- A binary language classification method used which will return if the input text is in Odia language or in any other non-Odia language. 
- Along with this a confidence score also returned. The score provides how confident the library is that it is Odia or Non-Odia.
- There is a `threshold` parameter to the method which can be configured to tune the confidence score threshold after which it will be regarded as Odia. The default value is 0.5.

```python
>>> from openodia import ud
>>> ud.detect_language("hey how are you?")
{'language': 'non-odia', 'confidence_score': 1.0}

>>> ud.detect_language("hey how are you? ନ୍ୟାଚୁରାଲ ଲାଙ୍ଗୁଏଜ ପ୍ରୋସେସିଂ")
{'language': 'odia', 'confidence_score': 0.66666}

>>> ud.detect_language("hey how are you? ନ୍ୟାଚୁରାଲ ଲାଙ୍ଗୁଏଜ ପ୍ରୋସେସିଂ", threshold=0.7)
{'language': 'non-odia', 'confidence_score': 0.333333}

>>> ud.detect_language("ନ୍ୟାଚୁରାଲ ଲାଙ୍ଗୁଏଜ ପ୍ରୋସେସିଂ ବା ପ୍ରାକୃତିକ ଭାଷା ପ୍ରକ୍ରିୟାକରଣ କଂପ୍ୟୁଟର ବିଜ୍ଞାନ ଏବଂ ଆର୍ଟିଫିସିଆଲ ଇଣ୍ଟେଲିଜେନ୍ସର ସେହି ବିଭାଗକୁ କୁହାଯ ାଏ ଯାହା ମନୁଷ୍ୟର ଭାଷାଗୁଡ଼ିକ ସହ କମ୍ପ୍ୟୁଟରର କଥାବାର୍ତ୍ତାକୁ ବୁଝାଇଥାଏ। ")
{'language': 'odia', 'confidence_score': 0.99404}
```
### :material-set-split: Word Tokenizer

- To tokenize odia text into multiple words or tokens `word_tokenizer` module can be used.

```python
>>> from openodia import ud
>>> ud.word_tokenizer("କ୍ୱାଣ୍ଟମ କମ୍ପ୍ୟୁଟିଙ୍ଗ, ହେଉଛି ଏକ ଉଦୀୟମାନ ହାର୍ଡ଼ୱେର ଏବଂ ସଫ୍ଟୱେରର ପ୍ରଯୁକ୍ତିବିଦ୍ୟା, ଯାହା କଠିନ ଗାଣିତିକ ସମସ୍ୟାଗୁଡ଼ିକର ସମାଧାନ ପାଇଁ ଉପ-ପାରମାଣବିକ ଘଟଣାଗୁଡ଼ିକର ଉପଯୋଗ କରିଥାଏ ।[୧]")
['କ୍ୱାଣ୍ଟମ', 'କମ୍ପ୍ୟୁଟିଙ୍ଗ', 'ହେଉଛି', 'ଏକ', 'ଉଦୀୟମାନ', 'ହାର୍ଡ଼ୱେର', 'ଏବଂ', 'ସଫ୍ଟୱେରର', 'ପ୍ରଯୁକ୍ତିବିଦ୍ୟା', 'ଯାହା', 'କଠିନ', 'ଗାଣିତିକ', 'ସମସ୍ୟାଗୁଡ଼ିକର', 'ସମାଧାନ', 'ପାଇଁ', 'ଉପ', 'ପାରମାଣବିକ', 'ଘଟଣାଗୁଡ଼ିକର', 'ଉପଯୋଗ', 'କରିଥାଏ', '।', '୧']
```

### :material-call-split: Sentence Tokenizer

- Tokenize a paragraph into multiple sentences.
- Only working on full stop.

```python
>>> from openodia import ud
>>> ud.sentence_tokenizer()
```

### :material-eye-remove: Remove stopwords

- Frequently occurring words in a language are called as _stopwords_. Using the below function you can remove the stopwords.
- Internally this method calls the `word_tokenize` method to get tokens from the text.
- As most of the time processing happens in list by default a list of strings will be returned.

```python
>>> from openodia import ud
>>> ud.remove_stopwords("ରାମ ଓ ସୀତା ଆମକୁ ଆଶୀର୍ବାଦ ଦେଇଛନ୍ତି")
['ରାମ', 'ସୀତା', 'ଆମକୁ', 'ଆଶୀର୍ବାଦ']
>>> ud.remove_stopwords("ରାମ ଓ ସୀତା ଆମକୁ ଆଶୀର୍ବାଦ ଦେଇଛନ୍ତି ", get_str=True)
'ରାମ ସୀତା ଆମକୁ ଆଶୀର୍ବାଦ'
```
Here the stopwords `ଓ` and `ଦେଇଛନ୍ତି` are removed from the text.

### :material-translate: Translation

- The translation module is a wrapper on top of Google Translate API.
- There are two translation methods provided:
    1. `odia_to_other_lang` and
    2. `other_lang_to_odia`

#### other_lang_to_odia

- As the name suggests this function can be used to translate from any other language to Odia language.
- If you are translating from any other language other than English, please provide the language code of it.

```python
>>> from openodia import other_lang_to_odia, odia_to_other_lang
>>> other_lang_to_odia("hello! feeling good?")
'ନମସ୍କାର!ଭଲ ଲାଗୁଛି?'
>>> other_lang_to_odia("शेयर बाज़ार एक ऐसा बाज़ार है जहाँ कंपनियों के शेयर खरीदे-बेचे जा सकते हैं।", source_language="hi")
'ଷ୍ଟକ୍ ମାର୍କେଟ୍ ହେଉଛି ଏକ ବଜାର ଯେଉଁଠାରେ କମ୍ପାନୀଗୁଡିକ କିଣାଯାଇପାରିବ |'
```

#### odia_to_other_lang

- This function can be used to translate an Odia text into another language.
- The same language code you can choose from as provided above.
- By default the function will trasnlate to English language.

```python
>>> odia_to_other_lang("ନମସ୍କାର!ଭଲ ଲାଗୁଛି?")
'Hello! Sounds good?'
```
### :material-shovel: Automatic extractive text summarization

Extracts the important summary snippet of a given text.

```python
>>> from openodia import WordFrequency
>>> wf = WordFrequency(
        text="ଭାରତୀୟ ସର୍ବୋଚ୍ଚ ନ୍ୟାୟାଳୟ, ଭାରତର ଉଚ୍ଚତମ ନ୍ୟାୟିକ ଅନୁଷ୍ଠାନ ଅଟେ ଏବଂ ଭାରତୀୟ ସମ୍ବିଧାନ ଅଧୀନସ୍ଥ "
        "ସର୍ବୋଚ୍ଚ ନ୍ୟାୟାଳୟ ଅଟେ । "
        "ଏହା ସର୍ବ ବରିଷ୍ଠ ସାମ୍ବିଧାନିକ ନ୍ୟାୟାଳୟ ଅଟେ ଏବଂ ଏହି ନ୍ୟାୟିକ ପୁନରାବଲୋକନର କ୍ଷମତା ରହିଛି । "
        "ଭାରତର ମୁଖ୍ୟ ବିଚାରପତି ଏହାର ମୁଖ୍ୟ ଅଟନ୍ତି । ତତ୍ସହିତ ଏଥିରେ ସର୍ବାଧିକ ୩୪ ଜଣ ବିଚାରପତି ଅଛନ୍ତି । "
        "ମୁଖ୍ୟ, ଅପିଲୀୟ ତଥା ପରାମର୍ଶିକ ଆଦି ଅଧିକାରକ୍ଷେତ୍ର ମାଧ୍ୟମରେ ଏହାର ବିସ୍ତୃତ କ୍ଷମତା ରହିଛି । "
        "ଏହା ଭାରତରେ ସବୁଠାରୁ ଶକ୍ତିଶାଳୀ ଲୋକାନୁଷ୍ଠାନ ବୋଲି ଧରାଯାଇଅଛି । "
        "ଦେଶର ସାମ୍ବିଧାନିକ ନ୍ୟାୟାଳୟ ହୋଇଥିବାରୁ, ଏହା ମୁଖ୍ୟତଃ ସଙ୍ଘର ବିଭିନ୍ନ ଉଚ୍ଚ ନ୍ୟାୟାଳୟ ତଥା "
        "ଅନ୍ୟାନ୍ୟ ନ୍ୟାୟାଳୟ ଓ "
        "ଟ୍ରିବ୍ୟୁନାଲମାନଙ୍କର ରାୟ ବିରୁଦ୍ଧରେ ଅପିଲ୍ ନିଏ । "
        "ଏହା ନାଗରିକମାନଙ୍କର ମୌଳିକ ଅଧିକାରର ରକ୍ଷାକରେ ଏବଂ ବିଭିନ୍ନ ସରକାରୀ ଅଧିକାରୀ ତଥା "
        "ଦେଶରେ କେନ୍ଦ୍ର ସରକାର ବନାମ ରାଜ୍ୟ ସରକାର କିମ୍ବା ଗୋଟିଏ ରାଜ୍ୟ ସରକାର ବନାମ ଅନ୍ୟ ରାଜ୍ୟ ସରକାର "
        "ମଧ୍ୟରେ ବିବାଦର ସମାଧାନ କରେ । "
        "ଏକ ପରାମର୍ଶଦାତା ହିସାବରେ, ଏହା ଭାରତୀୟ ସମ୍ବିଧାନ ଅନୁସାରେ ରାଷ୍ଟ୍ରପତିଙ୍କଦ୍ୱାରା ସୂଚୀତ ବିଭିନ୍ନ ବିଷୟବସ୍ତୁ "
        "ଉପରେ ଶୁଣାଣି କରିଥାଏ । ")
>>> wf.get_summary() # Auto threshold calculation
'ଭାରତୀୟ ସର୍ବୋଚ୍ଚ ନ୍ୟାୟାଳୟ, ଭାରତର ଉଚ୍ଚତମ ନ୍ୟାୟିକ ଅନୁଷ୍ଠାନ ଅଟେ ଏବଂ ଭାରତୀୟ ସମ୍ବିଧାନ ଅଧୀନସ୍ଥ ସର୍ବୋଚ୍ଚ ନ୍ୟାୟାଳୟ ଅଟେ  ଏହା ସର୍ବ ବରିଷ୍ଠ ସାମ୍ବିଧାନିକ ନ୍ୟାୟାଳୟ ଅଟେ ଏବଂ ଏହି ନ୍ୟାୟିକ ପୁନରାବଲୋକନର କ୍ଷମତା ରହିଛି  ଭାରତର ମୁଖ୍ୟ ବିଚାରପତି ଏହାର ମୁଖ୍ୟ ଅଟନ୍ତି  ତତ୍ସହିତ ଏଥିରେ ସର୍ବାଧିକ ୩୪ ଜଣ ବିଚାରପତି ଅଛନ୍ତି  ମୁଖ୍ୟ, ଅପିଲୀୟ ତଥା ପରାମର୍ଶିକ ଆଦି ଅଧିକାରକ୍ଷେତ୍ର ମାଧ୍ୟମରେ ଏହାର ବିସ୍ତୃତ କ୍ଷମତା ରହିଛି  ଏହା ଭାରତରେ ସବୁଠାରୁ ଶକ୍ତିଶାଳୀ ଲୋକାନୁଷ୍ଠାନ ବୋଲି ଧରାଯାଇଅଛି  ଦେଶର ସାମ୍ବିଧାନିକ ନ୍ୟାୟାଳୟ ହୋଇଥିବାରୁ, ଏହା ମୁଖ୍ୟତଃ ସଙ୍ଘର ବିଭିନ୍ନ ଉଚ୍ଚ ନ୍ୟାୟାଳୟ ତଥା ଅନ୍ୟାନ୍ୟ ନ୍ୟାୟାଳୟ ଓ ଟ୍ରିବ୍ୟୁନାଲମାନଙ୍କର ରାୟ ବିରୁଦ୍ଧରେ ଅପିଲ୍ ନିଏ  ଏହା ନାଗରିକମାନଙ୍କର ମୌଳିକ ଅଧିକାରର ରକ୍ଷାକରେ ଏବଂ ବିଭିନ୍ନ ସରକାରୀ ଅଧିକାରୀ ତଥା ଦେଶରେ କେନ୍ଦ୍ର ସରକାର ବନାମ ରାଜ୍ୟ ସରକାର କିମ୍ବା ଗୋଟିଏ ରାଜ୍ୟ ସରକାର ବନାମ ଅନ୍ୟ ରାଜ୍ୟ ସରକାର ମଧ୍ୟରେ ବିବାଦର ସମାଧାନ କରେ  ଏକ ପରାମର୍ଶଦାତା ହିସାବରେ, ଏହା ଭାରତୀୟ ସମ୍ବିଧାନ ଅନୁସାରେ ରାଷ୍ଟ୍ରପତିଙ୍କଦ୍ୱାରା ସୂଚୀତ ବିଭିନ୍ନ ବିଷୟବସ୍ତୁ ଉପରେ ଶୁଣାଣି କରିଥାଏ'

>>> wf.get_summary(threshold=3.0) # higher the threshold lesser the summary text
'ଭାରତୀୟ ସର୍ବୋଚ୍ଚ ନ୍ୟାୟାଳୟ, ଭାରତର ଉଚ୍ଚତମ ନ୍ୟାୟିକ ଅନୁଷ୍ଠାନ ଅଟେ ଏବଂ ଭାରତୀୟ ସମ୍ବିଧାନ ଅଧୀନସ୍ଥ ସର୍ବୋଚ୍ଚ ନ୍ୟାୟାଳୟ ଅଟେ  ଏହା ସର୍ବ ବରିଷ୍ଠ ସାମ୍ବିଧାନିକ ନ୍ୟାୟାଳୟ ଅଟେ ଏବଂ ଏହି ନ୍ୟାୟିକ ପୁନରାବଲୋକନର କ୍ଷମତା ରହିଛି  ଦେଶର ସାମ୍ବିଧାନିକ ନ୍ୟାୟାଳୟ ହୋଇଥିବାରୁ, ଏହା ମୁଖ୍ୟତଃ ସଙ୍ଘର ବିଭିନ୍ନ ଉଚ୍ଚ ନ୍ୟାୟାଳୟ ତଥା ଅନ୍ୟାନ୍ୟ ନ୍ୟାୟାଳୟ ଓ ଟ୍ରିବ୍ୟୁନାଲମାନଙ୍କର ରାୟ ବିରୁଦ୍ଧରେ ଅପିଲ୍ ନିଏ  ଏହା ନାଗରିକମାନଙ୍କର ମୌଳିକ ଅଧିକାରର ରକ୍ଷାକରେ ଏବଂ ବିଭିନ୍ନ ସରକାରୀ ଅଧିକାରୀ ତଥା ଦେଶରେ କେନ୍ଦ୍ର ସରକାର ବନାମ ରାଜ୍ୟ ସରକାର କିମ୍ବା ଗୋଟିଏ ରାଜ୍ୟ ସରକାର ବନାମ ଅନ୍ୟ ରାଜ୍ୟ ସରକାର ମଧ୍ୟରେ ବିବାଦର ସମାଧାନ କରେ'

```

### :book: Offline Dictionary

- An offline dictionary will be downloaded as soon as you install this library.
- Therefore, when you translate from English to Odia words/phrases it will hit the offline dictionary first, if not found it will go for the Google translate API.
- Google Translate API responses have been cached, therefore from the 2nd call onwards on the same term(s) it will fetch fast from the local in-memory cache.
- We have used [LRU (Least Recently Used) cache](https://realpython.com/lru-cache-python/) with a maximum size of 10000.

???+note "English to Odia translation Workflow"
    Therefore, we have two flows on English to Odia dictionary translation:
    
    1. English text --> Check in Offline dictionary --> Found --> Return result
    2. English text --> Check in Offline dictionary --> Not Found --> Check in Cache --> Found --> Return result from Cache
    3. English text --> Check in Offline dictionary --> Not Found --> Check in Cache --> Not Found --> Hit Google Translate API --> Update the Cache --> Return result

## :bug: Known Issues

- There are few issues in the code an be found [here](https://github.com/soumendrak/openodia/issues).
- Contributions are highly welcomed. :pray_tone2:

???+quote
    "In my dream of the 21st century for the State, I would have young men and women who put the interest of the State before them. They will have pride in themselves, confidence in themselves. They will not be at anybody’s mercy, except their own selves. By their brains, intelligence and capacity, they will recapture the history of Kalinga." - [Biju Pattnaik](https://en.wikipedia.org/wiki/Biju_Patnaik)

<!-- Citation -->
<hr>
To cite this page, please use:

```bibtex
@misc{OpenOdia,
    author       = {Soumendra Kumar Sahoo},
    title        = {OpenOdia Documentation},
    howpublished = {\url{https://www.openodia.soumendrak.com/}},
    year         = {2021}
}
```
