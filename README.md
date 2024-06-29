**Опис документації**
Ця документація описує user-service вимоги та реалізацію в рамках проєкту Projector.

**Вимоги**
1. Два типи користувачів: адмін роль та покупець роль
2. Покупці повинні мати можливість: 
  - виконати sign up (реєстрація)
  - sign in (вхід в профіль)
  - sign out (вихід з профілю)
  - переглянути та відредагувати свій профіль
3.Адміністратори повинні мати можливість:
виконати sign in (вхід в профіль) / sign out (вихід з профілю)
переглянути та відредагувати свій профіль
переглянути список покупців
заблокувати певного покупця від можливості робити замовлення

**Відкрити питання**
- Де зберегаємо користувачів та адмінів чи в json чи в базі даних?
- Змінити пароль функція потрібно чи ні? 
- Чи потрібно лист для підтвердження реєстрації?
- Чи потрібен генерувати токет користувача при вході або реалізувати через поле "sing in" = true/false?
- Якщо реалізація через токет, то генерувати його на вході?
- Чи необхідна рольова модель та як правильно її побудувати?
- Як і де заблокувати функції зміни статусу та перегляду користувачів? Коли користучач має "admin" = false ми блокуемо доступ функцій перегляду списку покупців та змінити "status" користувача
- 
**Функціонал**
1. Фіча "Sing up"
Для виконання функціоналу "Sing up" необхідно викликати функцію запис данних трьох полів: номер телефону, email, password. Всі поля вводять через термінал. Реалізувати перевірку полів на маску телефону, email та password. 
Після виконання функції дані записуються в json або в базу?_*питання_
Коли покупець вводить пароль при реєстрації ми шифруемо його та потім записуємо в json або в базу?_*питання_
При успішної реєстрації для користувача генеруються поля та призначаються наступні значення: "admin" = true/false? та "status" = true/false?

3. Фіча "Sing in"
Функція, що виводить два поля: номер телефону та пароль, де користувач через термінал вводить значенния. Коли функція виконується необхідна перевірка паролю по номеру телефону, щоб пароль співпадав. 
Після успішного співпадіння необхідно або змінити поле "sing in" = true/false? або згенерувати токен_*питання_

3. Фіча "Profile"
Виводиться наступні поля: ПІБ, номер телефону, email, адреса доставки. Та для того, щоб змінити значення в ціх полях, потрібно викликати функцію change, котра дозволить змінити записи у базі данних.
5. Фіча "Sing out" - коли користувач нажимає на вихід з профілю, то змінюється або поле на фолс або видаляється токет 

6. Фіча "Admin"
При перевірки "admin" = true/false, коли адмін true ми отримуємо доступ до двох функцій:
- Функція змінити поля "status" = true/false (котрий присваюється при реєстрації
- Функція get отримання списка користувачів з бази



