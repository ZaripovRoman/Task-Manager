# 1. Цель проекта
Цель проекта — разработать браузерное приложение, которое позволяет создавать собственные списки задач. 

# 2. Описание системы
Система состоит из следующих основных функциональных блоков:

1. Регистрация, аутентификация и авторизация
2. 

## 2.1. Регистрация
Для регистрации на вход приложению должны быть переданы следующие данные:

- email — обязательное поле
- имя и фамилия — обязательное поле
- телефон — опциональное поле

После отправки формы регистрации подписчика ему на email приходит письмо с первым кодом, по которому он может войти. Аутентификация будет происходить по разовым кодам, приходящим на email.

## 2.2. Аутентификация автора и подписчиков
Аутентификация автора и подписчиков осуществляется по email и одноразовому паролю (или по одноразовой ссылке), который приходит на этот email (как реализовано при входе в Skype у Microsoft).

## 2.4. Функционал для автора
Автор после аутентификации (ввода логина и пароля) получает доступ к своему автороскому функционалу в Системе. Этот функционал состоит из следующих блоков:

Редактирование данных профиля
Заведение и редактирование типов подписок
Заведение и редактирование контента
Заведение и редактирование целей
Рассылки
Аналитика

### 2.4.1. Заведение и редактирование целей
Автор может осуществлять в Системе сбор на какую-то цель. Для этого он создаёт (и может отредактировать впоследствии) цель, в рамках которой задаётся:

описание цели — небольшой текст с описанием того, на что собираются деньги
сумма к сбору в рублях
На публичной странице цель отображается с описанием и текущим прогрессом например, «107 775 из 130 000 руб. собрано»

Целей может быть несколько. Оплата цели — это разовый платёж, не рекуррентный, то есть не списывающийся ежемесячно.

### 2.4.2. Аналитика
Автор видит следующую аналитику:

Абсолютное и относительное количество подписчиков в разных уровнях подписки. Возможно в виде диаграмы pie-chart.

Платежи — списком, плюс экспорт в Excel всех платежей. Колонки: дата-время платежа, сумма платежа, период (для подписок, а не разовых платежей), подписчик — id (это длинный хеш из 32 символов, можно показывать по наведению мыши), имя, email.

## 2.5. Функционал оплаты подписки или разового платежа и главной страницы
Главная страница Системы — это список постов автора. Есть смотрит гость, то он видит только тизеры постов и посты, открытые для всех. На этой же странице видны возможные варианты подписки — с названием каждой подписки, описанием её, возможностью доступа в Telegram чат и ценой. Рядом с каждым типом подписки — кнопка Подписаться, ведущая на интерфейс входа или регистрации подписчика и последующей оплаты.

Рядом с каждым тизером скрытого поста должен отображаться необходимый для просмотра поста уровень подписки — или возможность купить этот отдельный пост за выставленную для него цену.

Пагинация постов осуществляется кнопкой «Показать ещё» внизу под уже показанными постами. Нажатие этой кнопки приводит к подгрузке и отображению более старых постов. Новые посты показываются сверху, старые — снизу.

Также должна быть возможность ставить лайки постам — возможность доступна только подписчикам. Количество лайков видно всем.

Должна быть возможность подписаться без оплаты. Таким людям будут приходить апдейты на почту.

При оплате подписки должна быть возможность оплатить сразу за 3, 6 или 12 месяцев (автор может настроить скидки на такие платежи).

Количество подписчиков должно показываться общим числом (и платные, и бесплатные) где-то на той же главной странице Системы.

У каждого поста должна быть своя постоянная ссылка, которую можно куда-то себе сохранить. Идентификатор поста, зашитый в ссылке, должен представлять собой UUID, не int число, чтобы нельзя было понять количество постов в системе.

## 2.6. Функционал для подписчика
Подписчик может смотреть посты и ставить им лайки, а также повышать свой уровень подписки и покупать отдельным платежом посты, не входящие в его подписку.

Комментариев под постами не подразумевается. Шеринг постов не подразумевается как отдельная кнопка — кто хочет пошерить, сделает это путём публикации ссылки. Можно отдельно показать только избранные посты.

Каждый пост можно добавить в избранное. В разделе избранное у подписчика должна быть возможность создавать тематические списки. При добавлении поста в избранное показать чек-боксами эти списки, в этот момент подписчик может сразу поместить пост в один из них.

Также у подписчика должна быть возможность на странице своего профиля отредактировать его данные (email, сменить пароль) и отменить подписку, что приведёт к остановке рекуррентных ежемесячных платежей и после даты окончания оплаченного периода подписчик становится бесплатным подписчиком.

В профиле должна быть возможность отключить email сообщения от системы.

# 3. Предлагаемый стек технологий
Для реализации системы предлагается следующий стек технологий:

Фронтенд:
AngularJS

# 4. Требования к дизайну
Минимализм, лаконичность, акцент на контент. Белый фон. Должен присутствовать логотип Приложения где-то на странице. Логотип надо разработать в рамках этого проекта.

В нижней части страницы (в подвале) должно быть написано:

«Работает на Open Source» со ссылкой на GitHub проекта.
