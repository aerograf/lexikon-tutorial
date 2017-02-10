# 4.0 Инструкция по эксплуатации

После установки и предварительной настройки модуля необходимо подогнать пункты меню и названия под Ваш сайт.
Делается это через файлы локализации /modules/lexikon/language/russian/
Файлы:
admin.php - локализация админ-панели
blocks.php - локализация блоков
main.php - локализация пользовательской части модуля
modinfo.php - локализация основных настроек модуля
waiting.php - локализация сообщений о публикации
В папке mail_template находятся файлы шаблонов писем, которые будут отправляться автоматически Вам и Вашим пользователям.
Если хотите что либо изменить, меняйте, но делайте резервную копию, что бы случайно не удалить при обновлении.
Оригинальные языковые файлы находятся /modules/lexikon/language/english/
После приведения модуля к желаемому результату, перейдите в админ панели в раздел шаблонов, и сгенерируйте шаблоны для модуля в Вашу тему.
Остальные действия производите с этиим файлами, т.к. при обновлении модуля, возможно потерять свои настройки шаблонов. Если появятся какието изменения в шаблонах модуля, можно перенести их вручную в Ваши шиблоны.
Обратите внимание на пункт настроек модуля 27.
Он позволяет предоставить Ваш контент модуля для размещения на других сайтах.
Шаблоны:
lx_content.tpl - шаблон представления блока для размещения на других сайтах с примером блока.
lx_syndication.tpl - шаблон блока, который будет размещен на другом сайте.
Можно сделать несколько вариантов, на Ваше усмотрение.
Если у Вас появляются псевдо символы в виде квадратиков, то необходимо посмотреть в адресной строке какой  файл вызывается. Зайти в него и разместить код:
(http://xoops.org/modules/newbb/viewtopic.php?post_id=362144)

if (! function_exists ( 'mb_ucfirst') && function_exists ( 'mb_substr')) {
   function mb_ucfirst ($ string) {
   $ String = mb_ereg_replace ( "^ [] +", "", $ string);
   $ String = mb_strtoupper (mb_substr ($ string, 0, 1, "UTF-8"), "UTF-8") mb_substr ($ string, 1, mb_strlen ($ string), "UTF-8").;
   return $ string;
   }
}

После этого пройти по файлу и заменить ucfirst на mb_ucfirst
И если у Вас на окончании слова или на конце появляются теже символы, то по аналогии, но размещать код нет необходимости заменить  substr на mb_substr.

По поводу добавления кириллицы в алфавитный указатель, пока вопрос не решен...