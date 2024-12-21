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
	<td>interface/vlan</td>
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