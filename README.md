# Реализация алгоритма спектральных вложений Грассмана-Штифеля
## в рамках библиотеки scikit-learn
### Горбачев Сергей Олегович, Группа 152
The project over 2 year of HSE Faculty of Computer Science 2016-2017

Задача актуальна, так как реализовывает достаточно [извеcтные] (http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.420.5053&rep=rep1&type=pdf) алгоритмы в одной из самой популярной библиотеки для ML, дополняя ее функционал.

Так как мы реализовываем алгоритмы для библиотеки scikit-learn, то иструменты: интерпретатор Python, сама библиотека scikit-learn и GitHub для хранения кода и отслеживания его изменения.

Контрольные точки:

КТ1: Документация по проекту и репозиторий

КТ2: "Out of sample" для алгоритма Multi-Dimensional Scaling, Spectral Embedding

КТ3: Recover of "Out of sample"

Реализованно OoS для Spectral Embedding для ядра KNN

* Пример использования:

```python
from sklearn import manifold

...

n_neighbors = 10
n_components = 2
se = manifold.SpectralEmbedding(n_components=n_components,
                                affinity="nearest_neighbors",
                                n_neighbors=n_neighbors)
Y = se.fit_transform(X)  # Where X - dataset and Y - embedding
Y_new = se.transform(X_new)  # Where X_new - new points and Y_new - thier embedding
```

Зависимости:

- Python (>= 2.6 or >= 3.3)
- NumPy (>= 1.6.1)
- SciPy (>= 0.9)

Сборка проекта:

- Необходимые для сборки пакеты под Ubuntu
  `sudo apt-get install build-essential python3-dev python3-setuptools python3-numpy python3-scipy libatlas-dev libatlas3gf-base`
- В корне проекта:
  `pip install`
- Тестирование:
  `python setup.py build_ext --inplace`
  `nosetests -v sklearn/`
