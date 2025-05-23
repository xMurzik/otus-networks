#  Лабораторная работа. Настройка и проверка расширенных списков контроля доступа.


###  Задание:

+ Часть 1. Создание сети и настройка основных параметров устройства
+ Часть 2. Настройка и проверка списков расширенного контроля доступа



### Топология:

![](./imgs/tp.png)


### Таблица адресации:


<table>

<tr>
	<td>Устройство</td>
	<td>Interface</td>
	<td>IP-адрес</td>
	<td>Маска подсети</td>
	<td>Шлюз по умолчанию</td>
</tr>

<tr>
        <td rowspan="6">R1</td>
        <td>E0/1</td>
	  <td>-</td>
	  <td>-</td>
	  <td>-</td>
</tr>

<tr>
        <td>E0/1.20</td> 
	  <td>10.20.0.1</td>
	  <td>255.255.255.0</td>
	  <td>-</td>
</tr>

<tr>
        <td>E0/1.30</td> 
	  <td>10.30.0.1</td>
	  <td>255.255.255.0</td>
	  <td>-</td>
</tr>

<tr>
        <td>E0/1.40</td> 
	  <td>10.40.0.1</td>
	  <td>255.255.255.0</td>
	  <td>-</td>
</tr>

<tr>
        <td>E0/1.1000</td> 
	  <td>-</td>
	  <td>-</td>
	  <td>-</td>
</tr>

<tr>
        <td>Loopback1</td> 
	  <td>172.16.1.1</td>
	  <td>255.255.255.0</td>
	  <td>-</td>
</tr>

<tr>
        <td>R2</td>
        <td>E0/1</td>
	  <td>10.20.0.4</td>
	  <td>255.255.255.0</td>
	  <td>-</td>
</tr>

<tr>
        <td>S1</td>
        <td>VLAN 20</td>
	  <td>10.20.0.2</td>
	  <td>255.255.255.0</td>
	  <td>10.20.0.1</td>
</tr>

<tr>
        <td>S2</td>
        <td>VLAN 20</td>
	  <td>10.20.0.3</td>
	  <td>255.255.255.0</td>
	  <td>10.20.0.1</td>
</tr>


<tr>
        <td>PC-A</td>
        <td>NIC</td>
	  <td>10.30.0.10</td>
	  <td>255.255.255.0</td>
	  <td>10.30.0.1</td>
</tr>


<tr>
        <td>PC-B</td>
        <td>NIC</td>
	  <td>10.40.0.10</td>
	  <td>255.255.255.0</td>
	  <td>10.40.0.1</td>
</tr>


</table>


### Таблица VLAN: 

<table>

<tr>
	<td>VLAN</td>
	<td>Имя</td>
	<td>Назначенный интерфейс</td>
</tr>


<tr>
	<td>20</td>
	<td>Mng</td>
	<td>S2: E0/3</td>
</tr>

<tr>
	<td>30</td>
	<td>Operations</td>
	<td>S1: E0/2</td>
</tr>

<tr>
	<td>40</td>
	<td>Sales</td>
	<td>S2: E0/1</td>
</tr>


<tr>
	<td>999</td>
	<td>Parking_lot</td>
	<td>Other interfaces</td>
</tr>

<tr>
	<td>1000</td>
	<td>Native</td>
	<td>-</td>
</tr>


</table>


### Домашнее задание: 

Выполним базовую настройку маршрутизаторов

![](./imgs/1.png)


Выполним базовую настройку коммутаторов

![](./imgs/2.png)


Создадим VLAN'ы на коммутаторах

![](./imgs/3.png)


Переведем порты на коммутаторе в соотв. с таблицей VLAN'ов и настроим транки

![](./imgs/4.png)
![](./imgs/4.1.png)
![](./imgs/4.2.png)
![](./imgs/4.3.png)
![](./imgs/4.4.png)

Проверим таблицу VLAN'ов

![](./imgs/4.5.png)

Добавим список разрешенных VLAN'ов на транк портах

![](./imgs/5.png)

Проверим таблицу транков на коммутаторах

![](./imgs/5.1.png)

Сохраним конфигурацию

![](./imgs/5.2.png)

Создадим и настроим саб-интерфейсы на R1

![](./imgs/6.png)

Добавим инкапсуляцию для нативного интерфейса e0/1.1000

![](./imgs/6.4.png)

Создадим loopback 1 на R1

![](./imgs/6.1.png)

Проверим таблицу интерфейсов на R1

![](./imgs/6.2.png)

Настроим интерфейс и маршрут по умолчанию на R2 

![](./imgs/6.3.png)

Создадим профиль для ssh соединения и ключ на маршрутизаторе

![](./imgs/7.png)

Настроим линии vty и ограничим доступ только по SSH

![](./imgs/7.1.png)

Проверим подключение к R1 по SSH

![](./imgs/7.2.png)

Также настроим SSH на остальных сетевых устройствах

![](./imgs/7.3.png)

Включим сервер HTTPS на R1

![](./imgs/19.1.png)

Настроим ip-адресацию на хостах

![](./imgs/9.png)

Исправим настройки разрешенных VLAN'ов на транк портах

![](./imgs/10.png)

Пропингуем адреса из таблицы. В качестве хостов я использовал роутеры тк VPC  не поддерживает SSH

![](./imgs/11.png)

Создадим Acl и повесим его на вход интерфейса e0/1.40

![](./imgs/12.png)

Проверим доступ по SSH с сети 10.40.0.0 к 10.20.0.0 и в первый раз получит положительный результат, но после активации acl соединение не создается, но если сделать подключение через lo1 то все ок

![](./imgs/13.png)

Запретим icmp запросы с сеток 10.40.0.0 к 10.20.0.0 и 10.30.0.0, но к другим разрешим и проверим

![](./imgs/14.png)

Создадим новый асл лист , который запрещает эхо запросы с сети 10.30.0.0 к 10.40.0.0, но остальные разрешены

![](./imgs/15.png)
![](./imgs/15.1.png)

Проверим, что правила работают

![](./imgs/15.2.png)

Выполним проверки в соотв. с таблицей 

![](./imgs/16.png)

Изменим маску в наших acl и выполним повторную проверку по таблице

![](./imgs/18.png)
![](./imgs/17.png)

Проверим доступ к http и https 

![](./imgs/20.png)