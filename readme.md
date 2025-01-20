# jcmc

## Фичи

- Тоггл коммандлайна [progress] 
- Xcode project [progress]

## Что это за бранч и репо?
Это мой личный форк репозитория mc из `https://github.com/johncapfull/mc/tree/master`
Рабочий бранч: jcdev

В него я периодически руками подсасываю апстрим по релизным тегам
Последний релизный тег, который был подсосан: `4.8.32`

## Подсос тегов из апстрима

Например, мы хотим поднять jcdev до уровня релиза 4.8.32. Как сделать:
```
git fetch --tags upstream
git checkout tags/4.8.32 -b release-4.8.32
```

Как был добавлен апстрим сюда (сделано ранее):
`git remote add upstream git@github.com:MidnightCommander/mc.git`


