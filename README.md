
# Настройка Sublime Text

1) Установить Sublime Text

```
sudo snap install sublime-text --classic
```

2) Установить Sublime Merge

```
sudo snap install sublime-merge --classic
```

3) Установить Package Control

https://packagecontrol.io/installation

4) Скопировать настройки

```
git clone https://github.com/6umpukc-uHKBu3umop/sublime-text-ide.git && cd sublime-text-ide && cp -r Packages/User/ ~/.config/sublime-text-3/Packages/
```

5) Подождать загрузки и установки плагинов

## Настройка Noverify

1) Установить https://github.com/VKCOM/noverify/blob/master/docs/install.md

```
sudo snap install go --classic
go get -u github.com/VKCOM/noverify
```

2) Добавить в ~/.profile и перезагрузится/перелогинится

```
if [ -d "$HOME/go/bin" ] ; then
    PATH="$HOME/go/bin:$PATH"
fi
```

3) Склонировать настройки phpstorm-stubs

`git clone https://github.com/JetBrains/phpstorm-stubs ~/bin/phpstorm-stubs`

4) Скопировать кастомные из `sublime-text-ide/phpstorm-stubs/bitrix`

## Запуск проверки php-файлов

https://github.com/VKCOM/noverify/blob/master/docs/linter-usage.md

```
noverify \
	--stubs-dir=$HOME/bin/phpstorm-stubs \
	--exclude='vendor/|tests/|.updates/' \
	--cache-dir="./upload/tmp/.noverify/" \
	--exclude-checks unused,mixedArrayKeys,arraySyntax,phpdoc,phpdocLint,phpdocType \
	--full-analysis-files=bitrix/modules/citrus.arealtypro/lib/export/vkontakte.php \
	bitrix/modules/

```
