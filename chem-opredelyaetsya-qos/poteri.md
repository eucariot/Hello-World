# Потери

Эта метрика говорит о том, сколько из отправленных источником пакетов дошло до адресата.  
Причиной потерь может быть проблема в интерфейсе/кабеле, перегрузка сети, битовые ошибки, блокирующие правила ACL.  
Что делать в случае потерь решает приложение. Оно может проигнорировать их, как в случае с телефонным разговором, где запоздавший пакет уже не нужен, или перезапросить его отправку — так делает TCP, чтобы гарантировать точную доставку исходных данных.  
  
![](https://habrastorage.org/webt/s9/vc/jj/s9vcjjwjb494cyrx19oby8ykvms.png)  
  
Как управлять потерями, если они неизбежны, в главе [Управление перегрузками](http://linkmeup.ru/uploads/sdsm-15-qos.html#MANAGEMENT).  
Как использовать потери во благо в главе [Предотвращение перегрузок](http://linkmeup.ru/uploads/sdsm-15-qos.html#AVOIDANCE).

