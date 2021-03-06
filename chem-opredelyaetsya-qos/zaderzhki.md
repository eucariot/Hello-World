# Задержки

Это время, которое необходимо данным, чтобы добраться от источника до получателя.  
  
![](https://habrastorage.org/webt/m6/xo/qa/m6xoqapl9y6v422k8c4d--xtmvm.png)  
  
Совокупная задержка складывается из следующих компонентов.  


* **Задержка сериализации** \(**Serialization Delay**\) — время, за которое узел разложит пакет в биты и поместит в линк к следующему узлу. Она определяется скоростью интерфейса. Так, например, передача пакета размером 1500 байтов через интерфейс 100Мб/с займёт 0,0001 с, а на 56 кб/с — 0,2 с.
* **Задержка передачи сигнала в среде** \(**Propagation Delay**\) — результат ограниченной скорости света. Физика не позволяет добраться из Нью-Йорка до Томска по поверхности планеты быстрее чем за 30 мс \(фактически порядка 70 мс\).
* **Задержки, вносимые QoS** — это томление пакетов в очередях \(**Queuing Delay**\) и последствия шейпинга \(**Shaping Delay**\). Об этом мы сегодня будем говорить много и нудно в главе [Управление перегрузками](http://linkmeup.ru/uploads/sdsm-15-qos.html#MANAGEMENT) и [Управление скоростью](http://linkmeup.ru/uploads/sdsm-15-qos.html#RATE-LIMIT).
* **Задержка обработки пакетов** \(**Processing Delay**\) — время на принятие решения, что делать с пакетом: lookup, ACL, NAT, DPI — и доставку его от входного интерфейса до выходного. Но в день, когда Juniper в своём M40 разделил Control и Data Plane, задержкой обработки стало можно пренебречь.

  
Задержки не так страшны приложениям, где не требуется спешка: обмен файлами, сёрфинг, VoD, интернет-радиостанции итд. И напротив, они критичны для интерактивных: 200мс уже неприятны на слух при телефонном разговоре.   
  
Связанный с задержкой термин, но не являющийся синонимом — **RTT** \(**Round Trip Time**\) — это путь туда-обратно. При пинге и трассировке вы видите именно RT, а не одностороннюю задержку, хотя величины и имеют корреляцию.  


