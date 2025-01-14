<p align="center">

 <img width="600" height="300" src="https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2019/08/eyecatch_git.png">
</p>

***

# Инструкция по работе с Git
### Скачайте и установите Visual Studio Code и Git на ваш персональный компьютер:
[VScode](https://code.visualstudio.com/) [Windows, Mac, Linux]
[Git](https://git-scm.com/downloads) [Windows, Mac, Linux]

**Необходимо проверить, установлена ли программа Git с помощью команды:**

```sh
    git --version
```
_Если Git **успешно установлен** на компьютер, то в терминале вы увидите его **версию**._
***

<p align="right">

 <img width="384" height="251" src="https://miro.medium.com/max/949/1*YryX-5FXvrpFGkh8PsdEGQ.png">

</p>

### Представьтесь Git.
После первого запуска необходимо **_представиться_** Git, используя команды:
```sh
    git config --global user.name «Ваше именя на латинице»
    git config --global user.email mail@example.com
```
***

### Создание Git-репозитория

1. Создайте папку, в которой будет размещен репозиторий Git.
2. Откройте папку в VScode.
3. С помощью команды **`git init`** инициализируйте (привяжите) папку к программе Git.

***

## ___Основные команды Git___

**1**. Для проверки текущего состояния, наличия изменений, которые необходимо зафиксировать/**"закомитить"** необходимо использовать команду
```sh
    git status
```
>Перед выполнением данной команды необходимо, использую комбинацию клавиш **Ctrl+S**, сохранить внесенные изменения, в противном случая **git status** ничего не отобразит. Потребность в сохранении можно определить по наличию белого круга рядом с названием вкладки, отображающей открытый файл в VScode.

**2**. Для подтверждения (_добавления_) изменений в указанном файле проекта для последующего коммита необходимо использовать команду

```sh
    git add «Имя файла»
```
> После команды **git add** необходимо ввести полностое название файла с указанием расширениея. Писать имя файла целиком не обязательно. Введя часть имени, можно нажать клавишу **Tab** для автоматического дозаполнения.


**3**. Для подтверждения (_добавления_) изменений во всех файлах проекта для последующего коммита можно использовать команду

```sh
    git add .
```


**4**. Для фиксации текущего сосотояния (комита) используйте команду

```sh
    git commit -m "Комментарий к комиту"
```
>После **-m (message)** в ковычках указываем комментарий для лучшего понимания содержания комита.

* Возможно использование `git commit -am "Комментарий к комиту`, где "a" - add, с целью уменьшения количества необходимых к исполнению команд. Данная команда позволяет сразу добавить (**git add**) и закомитить (**git commit**) внесенные изменения. **!!!Данная команда неприменима для только что созданных файлов!!! Перед ее использованием необходимо к новому файлу применить команду `git add`.**

**5**. Для вывода журнала в хронологическом порядке с указанием хэша, автора, даты и комментария комитов используйте команду

```sh
    git log
```
* Возможно также использованик команд:

| Команда  | Действие|
| :------------- | :------------- |
| `git log --oneline`  | Выводит журнал в сокращенном виде с указанием хэша и комментария  |
| `git reflog`  | Выводи журнал со всеми изменениями, не только отражающими создание комитов  |
>Для выхода из журнала необходимо нажать клавишу **q** 

**6**. Для переключения между версиями/*состояниями*/**комитами** используйте команду

```sh
    git checkout «Номер комита»
```
>Не обязательно писать весь номер комита, достаточно указать первые 4 символа. Для возврата в последнюю актуальную версию используйте команду **git checkout master**.

**7**. Для отображения разницы текущего и закомиченного состояния используйте команду 

```sh
    git diff
```
>Перед выполнением команды необходимо сохранить последние изменений, нажав комбинацию клавиш **Ctrl+S**.

* По умолчанию, данная команда сопостовляет текущее состояние с последним созданным комитом, но если после команды `git diff` добавить номер более раннего комита, то будут отображены все изменения с текущего момента до момента создания указанного комита.
<p align="right">
  <img width="280" height="280" src="https://ae01.alicdn.com/kf/H3e808aa0ed01439788d02165c35e18c90.jpg">
</p>

## Команды Git для работы с удаленным репозиторием
![git oCaTopus](https://github.githubassets.com/images/modules/site/social-cards/github-social.png)

**1.** Для клонирования внешнего репозитория на локальный ПК используйте команду:
```sh
    git clone <url-адре репозитория>
```
**2.** Для получения изменений и слияния с локальной версией примените команду:
```sh
    git pull
```
**3.** Для получения изменений и слияния с локальной версией примените команду:
```sh
    git push
```
> В некоторый случаях может потребоваться применение команды **`git pull --rebase`**, но в послдних версиях **Git** стандартная команда уже включает в себя расширенный функционал.

**4.** Для добавления новой ветки из локального репозитория в удаленный необходимо использовать команду:
```sh
git push --set-upstream origin <Название ветки>
```