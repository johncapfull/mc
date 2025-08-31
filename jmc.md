# jmc

Это мой личный форк репозитория mc из `https://github.com/johncapfull/mc/tree/master`

Рабочий бранч: jcm (раньше был jcdev)
Последний релизный тег: tags/4.8.33

Проект mc.sublime-project, сконфигурирован вместе с clangd.

> Статус: собран и используется

## Как собрать


```
./autogen.sh

./configure --disable-silent-rules --without-x --with-screen=slang --enable-vfs-sftp --prefix=/opt/homebrew/Cellar/midnight-commander/4.8.33 --libdir=/opt/homebrew/Cellar/midnight-commander/4.8.33/lib

# опционально --disable-debug

make

# --> Соберет в ./src/mc

# Подменяем нашим mc хоумбрющный
cp -rf ./src/mc /opt/homebrew/Cellar/midnight-commander/4.8.33/libexec/bin


# Как понять и найти инфу с чем собирали
./mc --configure-options
```


Где скины:
/opt/homebrew/Cellar/midnight-commander/4.8.33/share/mc/skins


## Фичи

- Тоггл коммандлайна [in progress] 
- Find: сделать строку поиска контента под строкой имени файла, а не справа
- Клик третьей копкой мыши переходит по текущему выбранному, чтобы колесиком навигироваться
- CopyToClipboard в редакторе по alt+c, который забинжен на cmd+c в iterm
- +Выпилен `use_persistent_buffer`, чтобы не висло (все равно общий буфер для cmdbar / ctrl+o не работает)
- +Xcode project (delme) -> deprecated, переехали в саблайм + clangd.

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


