# Работа с Git
---
1. Создадим папку для нового проекта и инициализируем новый git
```bash
mkdir /root/dev/second-project
cd /root/dev/second-project
git init
```
У нас появится папка .git, она скрытая, и чтобы ее увидеть, нужно запустить ls с ключом -a

2. Создадими отредактируем наш первый файл
```bash
touch README.md
nano README.md
```
Можно просто **README.md**

3. Чтобы наш git начал отслеживать изменения в этом файле, мы можем указать конкретно этот файл 
```bash
git add README.md 
```
или все файлы в этой директории и всех поддерикториях
```bash
git add .
```
4. После чего нам нужно зафиксироватиь состояние. Создать точку отката. Это делается с помощью коммита
```bash
git commit -m "Создали файл README.md"
```
5. Теперь нам нужно связать наш локальный репозиторий и удаленный на GitHub, который мы заранее сделали
```bash
git remote add origin git@github.com:host-ping/second-project2.git
```
Можем посмотреть связанные репозитории:
```bash
git remote -v
origin	git@github.com:host-ping/second-project2.git (fetch)
origin	git@github.com:host-ping/second-project2.git (push)
```
6. Отправим (запушим) наши изменения на удаленный репозиторий:
```bash
git push -u origin 
```

7. HEAD -- это голова.
Коммит -- это всему голова.
Статусы файлов: **modified+git add = staged**

<<<<<<< HEAD
=======
```mermaid
%% Статусы файлов:
graph LR;
  untracked -- "git add" --> staged;
  staged    -- "git commit" --> tracked/comitted;


>>>>>>> 2e652b33455a39e72f717ea366e69402c63ffa69
```mermaid
%% Статусы файлов:
graph LR;
  untracked -- "git add" --> staged;
  staged    -- "git commit" --> tracked/comitted;

