# Course_work

# Інструкція для запуску C++ проєкту

Щоб успішно запустити ваш проєкт на C++, дотримуйтесь наступних кроків:

---

## 1. Попередні вимоги
Перед тим як почати, переконайтеся, що у вас встановлено:
- **Компилятор C++** (наприклад, GCC, Clang або Microsoft Visual C++).
- **CMake**
- **Git**

---

## 2. Кроки для збірки та запуску Серверу

### a) Клонування репозиторію (за потреби)
Якщо проєкт зберігається у віддаленому репозиторії Git, виконайте:
```bash
git clone <URL_репозиторію>
cd <імя_папки_проєкту>
Завантажити докер
в терміналі прописати
docker build -t cpp-course-project .
docker run --name my_cpp_server -p 8080:8080 cpp-course-project
```
## 2. Кроки для збірки та запуску Клієнту

### a) Клонування репозиторію (за потреби)