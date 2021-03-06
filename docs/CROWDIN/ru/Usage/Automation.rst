Автоматизация
**************************************************

Что такое автоматизация
==================================================
Для одинаковых частых событий приходится изменять одни и те же параметры. Чтобы избежать лишней работы, можно автоматизировать событие, если вы можете описать его достаточно точно и позволить ему делать это автоматически. 

Например, при низкой ГК, вы можете решить, что должна автоматически установиться высокая временная цель. Или если вы находитесь в фитнес-центре, вы автоматически получаете временную цель. 

Перед использованием автоматизации следует уверенно овладеть ручным управлением ` временными целями <./temptarget.html> ` _ или переключением профиля. 

Убедитесь, что вы понимаете, как работает автоматизация перед настройкой первого простого правила. ** Вместо действий разрешите AAPS только показывать уведомления. * * Если вы уверены, что автоматизация инициируется в нужное время, замените уведомление реальным действием.

.. изображение:: ../images/Automation_ConditionAction_RC3.png
  :alt: условие автоматизации + действие

Как пользоваться
==================================================
Чтобы настроить автоматизацию, нужно дать ей заголовок, выбрать хотя бы одно условие и одно действие. 

Важное примечание
--------------------------------------------------
** Автоматизация по-прежнему активна при отключении цикла! **

Поэтому при необходимости деактивируйте правила автоматизации на это время. Это можно сделать, сняв галочку в поле слева от названия правила автоматизации.

.. изображение:: ../images/Automation_ActivateDeactivate.png
  :alt: Активировать и деактивировать правило автоматизации

Общие настройки
--------------------------------------------------
Есть некоторые ограничения:

* Значение ГК должно составлять от 72 до 270 мг/дл или от 4 до 15 ммоль/л.
* Процент профилирования должен составлять от 70% до 130%.
* Есть 5 минут ограничения по времени между выполнениями (и первым выполнением).

**Пожалуйста, будьте внимательны:**

* ** менее -2 означает: -3 и ниже (-4, -10 и т.д.) * *
* **более -2 означает: -1 и выше (-1, 0, +10 и т.д)**


Условие
--------------------------------------------------
Вы можете выбрать между несколькими условиями. Некоторые моменты здесь объясняются, но основное легко понять и оно не все здесь описано:

* условия соединения: можно иметь несколько условий и подключить их с помощью 

   * "И"
   * "Или"
   * "Исключающее или" (что означает, что если одно (и только одно из) условий применимо, то действие (действия) произойдет)
   
* Время vs. время повторения

   * время = одно событие времени
   * повторяющееся время = то, что происходит регулярно (напр. раз в неделю, каждый рабочий день и т. д.)
   
* расположение: в конфигураторе (автоматизация), можете выбрать местоположение сервиса, который хотите использовать:

  * Использовать пассивное расположение: AAPS принимает положения только в том случае, если другие приложения запрашивали его
  * Использовать расположение сети: расположение вашего Wifi
  * Используйте локатор GPS (Внимание! Может привести к чрезмерной разрядке аккумулятора!)
  
Действие
--------------------------------------------------
Можно выбрать одно или несколько действий: 

* начать врем цель 

   * должно быть между 72 мг/дл и 270 мг/дл (4 ммоль/л и 15 ммоль/л)
   * работает только в том случае, если нет предыдущей временной цели
   
* остановить врем цель
* уведомление
* процент профиля

   * должно быть от 70% до 130% 
   * работает только в том случае, если предыдущий процент составляет 100%

После добавления ваших действий, **не забудьте изменить значения по умолчанию** на те, которые требуются, нажав на значения по умолчанию.
 
.. образ:: ../images/Automation_Default_V2_5.png
  :alt: автоматизация по умолчанию vs. задать значения

Выбор правил автоматизации
-----
Для отбора правил автоматизации нажмите и удерживайте кнопку с четырьмя строками в правой части экрана и двигайтесь вверх или вниз.

.. изображение:: ../images/Automation_Sort.png
  :alt: Выбор правил автоматизации
  
Удаление правил автоматизации
-----
Чтобы удалить правило автоматизации, просто смахните его влево или вправо.

.. изображение:: ../images/Automation_Deletet.png
  :alt: Выбор правила автоматизации

Рекомендации и предостережения
==================================================
* Когда вы начинаете пользоваться средствами автоматизации или создаете новое правило, добавьте уведомление об этом, пока не убедитесь, что правило хорошо работает.
* Наблюдайте за результатами работы правила.
* Постарайтесь не делать условия слишком легкими (например, ЕСЛИ ГК > 80 мг/дл И ГК < 180 мг/дл)

    **Вдвойне важно, если правило активирует переключатель профиля!**
 
* Попробуйте использовать временные цели Temp Targets вместо переключателей профиля Profile Switches. Temp Targets не сбрасывают ` Autosens <../Usage/Open-APS-features.html#autosens> ` _ на 0.
* Убедитесь, что переключатели профиля создаются с осторожностью и желательно как крайняя мера.

    * Переключение профилей делает `Autosens <../Usage/Open-APS-features.html#autosens>`_ бесполезным минимум на 6 часов.

* Переключение профилей не сбросит профиль назад на базовый профиль

    * Вы должны создать еще одно правило, чтобы вернуть профиль или сделать это вручную!
    * Повышенный риск гипогликемии в случае, если время работы нового профиля не истечет или не сбросится назад на базовый профиль.

Примеры
==================================================
Это просто примеры вариантов настройки, не советы. Не воспроизводите их, не зная, что вы делаете или зачем вам это нужно. Ниже приведены два примера со снимками экрана.

* Переключение профилей для вашей повседневной деятельности (например, школа, тренажерный зал, выходные, рабочий день...) с использованием геолокации, wifi, времени и т. д.
* Настройка временной цели для решений на основе времени, геолокации...
* Настройка временной цели ожидаемый прием пищи на основе времени, геолокации...

Временная Цель Низкая ГК
--------------------------------------------------
.. изображение:: ../images/Automation2.png
  :alt: Автоматизация2

Это сделал человек, который хочет получить автоматическую цель гипо при гипогликемии.

Временная Цель Время Обеда
--------------------------------------------------
.. изображение:: ../images/Automation3.png
  :alt: Автоматизация3
  
Это пример настроек автоматизации человека, который обедает в одно и то же время в течение недели. Если он в определенное время (перед обедом) находится в определенном месте, то получает более низкую временную цель (ожидаемый прием пищи). Из-за союза "И" это происходит только в определенное время в определенном месте. Поэтому эта автоматизация не работает в любое другое время в этом месте или в то время, когда человек сидит дома или работает дольше. 

Неправильное использование автоматизации
--------------------------------------------------
Как и все системы, автоматизация может применяться неправильно. Это может привести к трудностям и даже опасности для здоровья. Примеры неправильного применения:

* Попытка полного переопределения алгоритма вместо помощи (напр. замена профиля вместо тюнинга базала, соотношения инсулин-углеводы IC и т. д.)
* Установка профиля для компенсации приема пищи
* Установка профиля без определения продолжительности
* Создание правил в одну сторону (т.е. делать что-то, но не отменять это другим правилом)
* Создание долгосрочных правил

Альтернативы
==================================================

Для опытных пользователей есть и другие возможности для автоматизации задач с помощью IFTTT или приложения Android под названием Automate. Некоторые примеры можно найти ` здесь <./automationwithapp.html> ` _.
