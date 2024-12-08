![image](https://github.com/user-attachments/assets/b6cc9fbe-ac53-44e2-a0ca-4831eca1bc4e)

# Syntactic processing of Brazilian Portuguese

Building on previous research investigating the [Volitive Construction of the Future in Portuguese](https://revistas.ufrj.br/index.php/diadorim/article/view/46378), this study applies techniques from Natural Language Processing (NLP) and Data Science to analyze the behavior of these constructions within the theoretical framework of Usage-Based Construction Grammar. The main idea is to explore and assess the tools available for preprocessing data in the Portuguese language. The dataset used in this study can be found in [D&G UFF](https://deg.uff.br/corpus-dg/).

**Mariana Gonçalves da Costa** [Programa de Pós-Graduação em Informática/UFRJ]\
Last updated: 08 December 2024 - Python 3.10 - Google Colab

-----

## Stopwords selection

``` Python
def select_stopwords(stopwords, word_classes, remove_list = None):
  """ Creates the list of stopwords according to the selected categories.

  Arguments:
    stopwordsdict (dict): The dictionary containing all stopwords categorized by word classes.
    word_classes (list): The list of word classes to be included in the stopwords:
    (artigos, pronomes, preposicoes, adverbios, verbos).
    remove_list (list, optional): The list of words to be removed from the stopwords. Defaults to None.

  Returns:
    stopwords (list): a list of stopwords.
  """

  stopwords = [word for word_class in word_classes for word in stopwordsdict.get(word_class, [])]
  # Use dict.get() to avoid KeyError if a word class isn't present in the dictionary.

  # Remove specified words from the stopwords list if remove_list is provided
  if remove_list:
      stopwords = [word for word in stopwords if word not in remove_list]

  return stopwords
```
