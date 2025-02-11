**Функциональный объект или функтор** - это объект класса или структуры, который может быть вызван в качестве функции благодаря перегрузке оператора вызова функции `operator()`.

``` cpp
class MyFunctor {
public:
	int operator()(int x) const {
		return x * x;
	}
}
```

Одним из ключевых преимуществ функторов перед обычными функциями является возможность иметь внутреннее состояние.

Состояние функтора - это набор данных, хранящихся внутри объекта функтора.

``` cpp
class CallCounter {
private:
	int count;
public:
	CallCounter() : count(0) {}

	int operator()() {
		return ++count;
	}
};
```

Основными преимуществами функторов по сравнению с обычными функциями являются:

- Состояние функтора инкапсулировано внутри объекта

- Функторы с состояние могут быть легко повторно использованы в различных контекстах, так как, так они могут изменять своё состояние.