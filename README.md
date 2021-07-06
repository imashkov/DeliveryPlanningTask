# DeliveryPlanningTask
Проект решает оптимизационную задачу планирования доставок:
Имеется определённое количество поставщиков и потребителей. Известны объёмы товаров, поставляемых каждым поставщиком за весь период планирования. 
Известны объёмы товаров, которые поставщики могут поставить в каждый такт времени, и объёмы товаров, которые потребители могут потребить в каждый такт времени. 
Необходимо определить максимальный объём товара, который может быть сбыт, учитывая, что каждый потребитель сотрудничает только с определёнными поставщиками. 

Для решения данные задачи были представлены в виде транспортной сети (ор. граф), что позволило решить ее с помощью алгоритма Форда-Фолкерсона.

# Надстройки над базовой задачей.
Помимо базовой задачи, решено еще 2, основанные на ней:
1) Добавилось условие складирования, каждый потребитель в каждый такт времени (кроме последнего) может складировать не употреблённый товар.
В этой постановке необходимо найти минимальную вместимость склада, чтобы величина потока была максимальной.
Для решения используется бинарный поиск.
2) Считаем что вместимость у складов бесконечна. Необходимо найти минимальное множество потребителей, которым склад необходим.
Задача решается жадным алгоритмом: в определенном порядке склады исключаются у потребителей, при условии что поток не меняется.
Порядок определяется двумя сортировками по выбору.