# Mermaid_training

## 1.1

```mermaid
flowchart TD
    A[Начало] --> B[Заварка чая]
    B --> C[Есть чай?]
    C -->|Да| D[Вскипятить воду]
    C -->|Нет| E[Смерть]
    D --> G{Заварить чай}
    G --> H[Есть вкусняшки?]
    H -->|Да| I[Ура]
    H -->|Нет| X[Смерть]
```
## 1.2

```mermaid
sequenceDiagram
    participant Клиент
    participant Приложение
    participant Сервер
    participant Водитель

    Клиент->>Приложение: Вызов такси
    Приложение->>Сервер: Запрос на поиск
    Сервер->>Водитель: Новый заказ
    Водитель-->>Сервер: Принятие заказа
    Сервер-->>Приложение: Данные водителя
    Приложение-->>Клиент: Заказ принят
    Водитель->>Клиент: Забирает клиента
```

## 2.1

```mermaid
classDiagram
    class Library {
        +Book[] books
        +User[] users
    }

    class User {
        +String name
        +String userId
        +Book[] borrowedBooks
    }

    class Book {
        +String title
        +String author
        +String ISBN
        +Boolean isAvailable
    }

    Library "1" *-- "*" Book : contains
    Library "1" *-- "*" User : manages
    User "1" -- "*" Book : borrows
```



## 2.2

```mermaid
gantt
    title Разработка мобильного приложения
    dateFormat  DD-MM
    axisFormat %d/%m
    
    section Выполнение задач
    Разработка :crit, 01-01, 12d
    Направление задач : 13-01, 4d
    
    section Этапы проекта
    Этап 1 : 01-01, 11d
    Этап 2 : 12-01, 4d
    Этап 3 : 13-01, 4d
    Этап 4 : 14-01, 4d
    Этап 5 : 15-01, 4d
    Этап 6 : 16-01, 4d
    Этап 7 : 17-01, 4d
    Этап 8 : 18-01, 4d
    Этап 9 : 19-01, 4d
    Этап 10 : 20-01, 4d
    Этап 11 : 21-01, 4d
    Этап 12 : 22-01, 4d
    Этап 13 : 23-01, 4d
```



## 3.1

```mermaid
flowchart TD
    subgraph Frontend [Frontend]
        A[React]
        B[Redux]
        C[React Router]
        
        A --> B
        B --> C
    end

    subgraph Backend [Backend]
        D[Node.js]
        E[Express]
        
        D --> E
    end

    subgraph External [External Services]
        F[Stripe]
        G[SendGrid]
        H[MongoDB]
    end

    Frontend --> Backend
    Backend --> External
```





## 3.2

```mermaid
stateDiagram-v2
    [*] --> Новый
    Новый --> Подтвержденный : подтвердить
    Подтвержденный --> Оплаченный : оплатить
    Подтвержденный --> Отмененный : отменить
    
    Оплаченный --> Отправленный : отправить
    Оплаченный --> Отмененный : отменить
    
    Отправленный --> Доставленный : доставить
    Отправленный --> Возвращенный : вернуть
    
    Доставленный --> Возвращенный : инициировать возврат
    Доставленный --> [*] : завершить
    
    Возвращенный --> [*] : завершить
    Отмененный --> [*] : завершить
```

## 4.1

```mermaid
journey
    title User Journey Map: Покупка билетов в кино
    section Поиск фильма
      Просмотр афиши: 5: Пользователь
      Выбор фильма: 4: Пользователь
    section Выбор сеанса
      Выбор времени: 4: Пользователь
      Проверка расписания: 3: Пользователь
    section Выбор мест
      Просмотр схемы зала: 5: Пользователь
      Выбор удобных мест: 5: Пользователь
    section Оплата
      Ввод данных карты: 2: Пользователь
      Подтверждение оплаты: 4: Пользователь
    section Получение билетов
      Получение на email: 5: Пользователь
      Сохранение билетов: 4: Пользователь
    section Завершение
      Подготовка к походу: 5: Пользователь
```


# 4.2

```mermaid
erDiagram
    USERS {
        int id PK
        string name
        string email
        datetime created_at
    }
    
    POSTS {
        int id PK
        text content
        int author_id FK
        datetime created_at
    }
    
    COMMENTS {
        int id PK
        text content
        int post_id FK
        int author_id FK
        datetime created_at
    }
    
    LIKES {
        int user_id FK
        int post_id FK
        datetime created_at
    }
    
    SUBSCRIPTIONS {
        int subscriber_id FK
        int target_id FK
        datetime created_at
    }

    USERS ||--o{ POSTS : creates
    USERS ||--o{ COMMENTS : writes
    USERS ||--o{ LIKES : gives
    POSTS ||--o{ COMMENTS : has
    POSTS ||--o{ LIKES : receives
    USERS ||--o{ SUBSCRIPTIONS : "subscribes from"
    USERS }o--o{ SUBSCRIPTIONS : "subscribes to"
```



## 6

```mermaid
pie title Доли рынка
    "Отечественные" : 45
    "Иномарки" : 55
```