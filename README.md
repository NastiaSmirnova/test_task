# Тестовое задание для проекта  — Универсальный семантический энкодер текстов
Задача: Написать пайплайн валидации и тестирования экспериментов для сравнения качества задачи получения векторных представлений текста

Файл с решением: https://colab.research.google.com/drive/1lHWTS4TmlJQC-XH5iWqQQb_y5fjRncYJ?usp=sharing

Для анализа был выбран классический датасет imdb, который содержит пользовательские отзывы про фильмы. Рассмотрим его в контексте задачи определения тональности текста, то есть определения является ли отзыв положительным или отрицательным.

Гипотеза: Модель классификации с использованием эмбеддингов BERT покажет лучшую точность, чем модель на основе простых эмбеддингов слов
Выберем следующие метрики: 
1) Accuracy - поскольку это основная метрика-показатель качества классификации
2) Precision-Recall - важно смотреть при дисбалансе классов, одной точности может быть недостаточно
3) F1-мера - как объединение предыдущих метрик, поскольку стоит смотреть еще и их среднее
4) ROC-AUC - беру в качестве метрики которая будет измерять качество классификатора, основываясь на его способности различать классы

Для эксперимента возьмем три варианта построения векторного представления текста:
1) Word2Vec
2) Glove
3) Bert

Оценим полученные результаты:

![image](https://github.com/NastiaSmirnova/test_task/assets/47783751/b8051608-1807-4010-bda0-edfcb4b6e597)

Таким образом, гипотеза подтвердилась, для данного набора данных лучше всего себя показал BERT.
