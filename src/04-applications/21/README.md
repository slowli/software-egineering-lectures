---
title: Интерфейсы в программировании
category: Разработка современных программных систем
---

Под интерфейсом в программной инженерии подразумевается 
связь между компонентами программной системы, целью которой является описание способа обмена информацией. 
Использование интерфейсов позволяет сосредоточиться на том, *что* делает определенный модуль, и абстрагироваться от 
особенностей того, *как* он это делает.

Интерфейс — ключевое понятие в задаче интеграции. При разработке любой программы непременно приходится использовать 
«чужие» компоненты, такие как встроенная библиотека типов 
и стандартных функций или сторонние библиотеки. Более сложные приложения могут сами состоять из многих компонентов, которые надо 
интегрировать между собой; зачастую эта задача усложняется тем, что взаимодействующие модули написаны 
на различных языках программирования и функционируют в различных операционных средах.

Выделяют две категории программных интерфейсов:

  * **API** (application programming interface) описывает принципы взаимодействия на уровне исходного кода приложений. 
    Пример такого описания — декларации структур данных и функций (или объектов / классов в ООП).
  * **ABI** (application binary interface) специфицирует взаимодействие на уровне машинного кода. Например, 
    ABI может задавать особенности вызова функций (размещение операндов в стеке / регистрах), 
    размеры базовых типов данных и тому подобное.

Языки программирования высокого уровня (Java, Python, C#) скрывают от разработчиков пользовательских приложений особенности ABI, 
перекладывая ответственность за соблюдение стандартов на компилятор или интерпретатор языка. С другой стороны, 
роль ABI чрезвычайно велика при написании системных программ.

Интерфейсы могут использоваться как в пределах одного языка программирования, так и при интеграции модулей, 
реализованных на различных языках. Самый базовый тип интерфейсов первого рода — описание функций и типов данных. 
В большинстве языков программирования существуют средства для разделения интерфейса и реализации (например, файлы заголовков в C/C++), 
interface в Java или утиная типизация. Еще один способ интеграции — [инверсия управления][1], при которой под интерфейсами 
подразумеваются точки перехвата контроля управления разрабатываемым приложением.

Взаимодействие компонентов, реализованных на различных ЯП, отличается большей сложностью. В случаях, если компоненты выполняются 
в пределах одной среды (например, Java Virtual Machine или Common Lanuguage Runtime), интеграция по своей сути не отличается 
от интеграции компонентов на одном ЯП. Например, большинство сред выполнения задают общую для всех поддерживаемых языков 
систему типов данных, принципы управления памятью и так далее. Еще один способ взаимодействия — интерфейс внешних функций — 
обычно используется для вызова низкоуровневых утилит (это позволяет повысить скорость работы или использовать 
специфичный для платформы код). Наконец, для связи между ЯП высокого уровня могут использоваться программы-посредники (*middleware*), 
такие как CORBA.

[1]: http://martinfowler.com/bliki/InversionOfControl.html
