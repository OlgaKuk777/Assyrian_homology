# Assyrian_homology
The project was created as part of the coursework "Spot the Bot: Development of Methods for Enhancing Lemmatization and Digitization of Photos, Construction of Embeddings for the Assyrian Language"

## Структура проекта:

process_text_main.ipynb - основной код для запуска препроцессинга художественных текстов + обучение модели для художественных текстов

process_photo_main.ipynb - основной код для запуска препроцессинга газетных текстов + обучение модели для газетных (или комбинированных) текстов + автоматизированный перевод словесных последовательностей гомологий

process_julia.ipynb - основной код для запуска построения семантического пространства. вычисления гомологий

### Папка **sources**
output_all_non_clean.txt - исходные объединённые текстовые фалйы художественной литературы
recognized_all_gpt_new.txt - исходные оцифрованные тексты из газет

### Папка **texts: lemmatization and preprocessing** - результаты препроцессинга художественной литературы
output_all.txt - очищенные объединённые документы (пункт 1 в process_text_main.ipynb, и далее)
output_lemmatized_all.txt - разобранные парсером документы (пункт 2)
not_lemma.txt - нелемматизированные слова (пункт 2)

prob_lemmatized_not_lemma.txt - файл с подобранными примерными леммами после fuzzywuzzzy (библиотека с методом сравнения по нечёткому соответствию с предложенными леммами к нелемматизированным словам), пункт 3.1
prob_lemmatized_not_lemma_unique.txt - тот же prob_lemmatized_not_lemma.txt, но без дубликатов (пункт 3.2)
prob_lemmatized_all.txt - автоподбор лучшей примерной леммы в файле prob_lemmatized_not_lemma.txt после fuzzywuzzzy (пункт 3.2)
problem_lemmatized.txt - так и не нелемматизированные слова после fuzzywuzzzy (пункт 3.2)

**output_lemmas_sentences_filtered.txt - итоговые лемматизированные отфильтрованные предложения (пункт 4.2)**

### Папка **photos: lemmatization and preprocessing** - результаты препроцессинга газет
not_punct.txt - очищенные нормализованные предложения (пункт 1 в process_photo_main.ipynb, и далее)
named_entities.txt - файл с именованными сущностями (пункт 2)
lemmatized_not_punct_all.txt - разобранные парсером предложения (пункт 3)
not_lemma_with_photo.txt - нелемматизированные слова (пункт 3)

prob_lemmatized_not_lemma_photo_all.txt - файл с подобранными примерными леммами после fuzzywuzzzy (библиотека с методом сравнения по нечёткому соответствию с предложенными леммами к нелемматизированным словам), (пункт 4)
prob_lemmatized_not_lemma_photo_unique.txt - тот же prob_lemmatized_not_lemma_photo_all.txt, но без дубликатов (пункт 5)
prob_lemmatized_photo_all_final.txt - автоподбор лучшей примерной леммы в файле prob_lemmatized_not_lemma_photo_all.txt (пункт 5)
prob_lemmatized_photo_problem.txt - так и не нелемматизированные слова после fuzzywuzzzy (пункт 5)

photo_problems.txt - объединённые так и не нелемматизированные слова, проблемные слова (пункт 6)
**photo_sentences_filtered_new.txt  - лемматизированные отфильтрованные предложения (пункт 8)**

### Папка **general: fiction and newspapers** - художественные + газетные документы
**general_sentences_filtered.txt - все лемматизированные предложения, комбинированный файл художественных и газетных предложений (пункт 9)**

### Папка **embeddings**
urmi_dictionary.txt - текстовый файл с эмбеддингами слов художественных текстов
urmi_dictionary_photo_new.txt - текстовый файл с эмбеддингами слов газетных текстов
urmi_dictionary_general.txt - текстовый файл с эмбеддингами слов художественных + газетных текстов
urmi_embeddings.npz - NPZ файл с эмбеддингами слов художественных текстов
urmi_embeddings_photo_new.npz - NPZ файл с эмбеддингами слов газетных текстов
urmi_embeddings_general.npz - NPZ файл с эмбеддингами слов художественных + газетных текстов

### Папка **dictionaries**
lexemes.txt -  файл в основе uniparser-urmi, в котором представляет словарь с описанием каждой лексемы
paradigms.txt - файл в основе uniparser-urmi, содержащий формообразовательные парадигмы изменения лексем
Khan (2016) The Neo-Aramaic dt of Assyrian Christians of Urmi.pdf - пдф общая грамматика новоарамейских
