# Лабораторная работа - Реализация DHCPv4 


###  Задание:

+ Часть 1. Создание сети и настройка основных параметров устройства
+ Часть 2. Настройка и проверка двух серверов DHCPv4 на R1
+ Часть 3. Настройка и проверка DHCP-ретрансляции на R2


### Топология:

![](./imgs/tp.png)

### Таблица адресации:

<table>

<tr>
	<td>Устройство</td>
	<td>Интерфейс</td>
	<td>IP-адрес</td>
	<td>Маска подсети</td>
	<td>Шлюз по умолчанию</td>
</tr>

<tr>
        <td rowspan="5">R1</td>
        <td>G0/0/0</td>
	  <td>10.0.0.1</td>
	  <td>255.255.255.252</td>
	  <td rowspan="5">-</td>
</tr>

<tr>
        <td>G0/0/1</td>
	  <td>-</td>
	  <td>-</td>
</tr>

<tr>
        <td>G0/0/1.100</td>
	  <td></td>
	  <td></td>
</tr>

<tr>
        <td>G0/0/1.200</td>
	  <td></td>
	  <td></td>
</tr>

<tr>
        <td>G0/0/1.1000</td>
	  <td>-</td>
	  <td>-</td>
</tr>

<tr>
        <td rowspan="2">R2</td>
        <td>G0/0</td>
	  <td>10.0.0.2</td>
	  <td>255.255.255.252</td>
	  <td rowspan="2">-</td>
</tr>

<tr>
        <td>S1</td>
        <td>VLAN 200</td>
	  <td></td>
	  <td></td>
	  <td></td>
</tr>

<tr>
        <td>S2</td>
        <td>VLAN 1</td>
	  <td></td>
	  <td></td>
	  <td></td>
</tr>

<tr>
        <td>PC-A</td>
        <td>NIC</td>
	  <td>DHCP</td>
	  <td>DCHP</td>
	  <td>DHCP</td>
</tr>

<tr>
        <td>PC-B</td>
        <td>NIC</td>
	  <td>DHCP</td>
	  <td>DHCP</td>
	  <td>DHCP</td>
</tr>

</table>