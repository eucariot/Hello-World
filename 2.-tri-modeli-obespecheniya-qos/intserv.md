# IntServ

Заблаговременное резервирование ресурсов для потока на всём протяжении от источника до получателя.  
  
В растущий бессистемно Интернет отцы сетей MIT, Xerox, ISI решили добавить элемент предсказуемости, сохранив его работоспособность и гибкость.  
Так в 1994 году родилась идея IntServ в ответ на стремительный рост реал-тайм трафика и развитие мультикаста. Сокращалась она тогда до IS.  
Название отражает стремление в одной сети одновременно предоставлять услуги для реал-тайм и не-реал-тайм типов трафика, предоставив, при этом первым приоритетное право использования ресурсов через резервирование полосы. Возможность переиспользования полосы, на которой все и зарабатывают, и благодаря чему IP выстрелил, при этом сохранялась.   
  
Миссию по резервированию возложили на протокол RSVP, который для **каждого** потока резервирует полосу на **каждом** сетевом устройстве.  
Грубо говоря, до установки TCP сессии или начала обменом данными, конечные хосты отправляют RSVP Path с указанием требуемой полосы. И если обоим вернулся RSVP Resv — они могут начать коммуницировать. При этом, если доступных ресурсов нет, то RSVP возвращает ошибку и хосты не могут общаться или пойдут по BE.  
  
Пусть теперь храбрейшие из читателей представят, что для **любого** потока в интернете сегодня будет сигнализироваться канал заранее. Учтём, что это требует ненулевых затрат CPU и памяти на **каждом** транзитном узле, откладывает фактическое взаимодействие на некоторое время, становится понятно, почему IntServ оказался фактически мертворожденной идеей — нулевая масштабируемость.  
В некотором смысле современная инкарнация IntServ — это MPLS TE с адаптированной под передачу меток версией RSVP — RSVP TE. Хотя здесь, конечно же не End-to-End и не per-flow.  
  
IntServ описан в [RFC 1633](https://tools.ietf.org/html/rfc1633).  
Документ в принципе любопытен, чтобы оценить, насколько можно быть наивным в прогнозах.  


