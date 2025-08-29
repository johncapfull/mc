# jmc

Текущий бранч: release-4.8.33
Рабочий бранч: jcdev (пока не используется?)
Это мой личный форк репозитория mc из `https://github.com/johncapfull/mc/tree/master`


## Как собрать

Проект mc.sublime-project, сконфигурирован вместе с clangd.

```
./autogen.sh
./configure --disable-silent-rules --without-x --with-screen=slang --enable-vfs-sftp
make

# --> Соберет в ./src/mc
```


## Фичи

- Тоггл коммандлайна [progress] 

Не делаем:
- Xcode project -> deprecated, переехали в саблайм + clangd

## Где установлен в homebrew?

```
/opt/homebrew/Cellar/midnight-commander/4.8.33
```

Формула:
https://github.com/Homebrew/homebrew-core/blob/b7f2319966f1b601c21fcd7b9b412f8cf25593f3/Formula/m/midnight-commander.rb

## Что это за бранч и репо?


В него я периодически руками подсасываю апстрим по релизным тегам
Последний релизный тег, который был подсосан: `4.8.32`

## Как делал конфиг clangd
```
brew install bear
bear -- make

# --> появился файл compile_commands.json
```

## Подсос тегов из апстрима


Например, мы хотим поднять jcdev до уровня релиза 4.8.32. Как сделать:
```
git fetch --tags upstream
git checkout tags/4.8.33 -b release-4.8.33

# git checkout tags/4.8.32 -b release-4.8.32

```




Как был добавлен апстрим сюда (сделано ранее):
`git remote add upstream git@github.com:MidnightCommander/mc.git`


