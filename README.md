# AutoDeco (Geode mod)

Кнопка **AutoDeco** в левом верхнем углу редактора → выбор стиля (10 шт.), **Generate Deco**, **Remove Generated Deco**.

## Сборка `autodeco.geode`
Локально (нужны Geode CLI, SDK, компилятор):
```
geode sdk install && geode sdk install-binaries
export GEODE_SDK=<путь к SDK>
geode build        # -> build/user.autodeco.geode
```
Переименуйте в `autodeco.geode` при желании (или положите `user.autodeco.geode` в папку `geode/mods`).

Без установки: загрузите проект на GitHub → Actions → Build AutoDeco → артефакт `autodeco` с `.geode`.

## Как это работает
- Анализ: сетка solid-блоков, открытые грани (верх/бока), границы уровня.
- Декор ставится только если созданный объект — чистая Decoration (иначе удаляется) → геймплей не меняется.
- Все созданные объекты в группе 9999: Remove удаляет только их; повторная генерация заменяет прошлую декорацию. Оригинальные объекты не трогаются.
- ID объектов по стилям — таблица `styles()` в `src/main.cpp`; правьте под свои любимые декор-объекты.
