# YouTube PopUp jQuery Plugin Для DataLife Engine
Доработка плагина для использования в шаблона DLE CMS. Например для RSS информеров в которых используются ссылки на youtube ролики.
Исходный плагин, перенесен в структуру папок шаблона DLE.

## Что в комплекте:
- папка [DLE-CMS] содержит готовый набор для добавления в свой шаблон.
- папка [original] содержит исходную версию модуля.


## Улучшения 
1. Добавлен ключ ?rel=0 
для запрета отображения чужих роликов в качестве похожих видео.


## Установка в DLE 

1. Загрузить содержимое папки DLE-CMS/tempaltes/{THEME} в ваш шаблон на сайте.

2. В файле *main.tpl* найти место подключения jQuery, напоминаю, что он уже есть в любой версии DLE.
Обычно он загружается переменной *{jsfiles}{AJAX}* если скрипты вынесены в коней файла.

Или перед закрывающим тегом 

    </body>
    
Если используется классический способ подключения стилей и JS.     

После jQuery Вставить:

    {* YouTube_PopUp *}
    <link rel="stylesheet" type="text/css" href="{THEME}/assets/youtubepopup/YouTubePopUp.css">
    <script type="text/javascript" src="{THEME}/assets/youtubepopup/YouTubePopUp.jquery.js"></script>
    <script type="text/javascript">
      jQuery(function(){
          jQuery("a.bla-1").YouTubePopUp();
          jQuery("a.bla-2").YouTubePopUp( { autoplay: 0 } ); // Disable autoplay
      });
    </script>

3. В шаблоне RSS информера informet.tpl для загрузки роликов по клику на картинку-превью с ютуба
использовать код

    <a class="bla-1" href="{link}">
	    <img class="img-responsive" src="{image-1}" alt="" title="Смотрите видео: {news}">
	</a>

Где класс bla-1 - открытие модального окна с автоматическим запусков видео,
а класс bla-2 - открытие окна с отключенным автозапуском видео.

4. Если же необходимо добавить запуск окна с плеером YouTube для всех ссылок на сайте, которые ведут на https://www.youtube.com/ тогда добавьте


		$('a[href^="https://www.youtube.com/"]').addClass("bla-2");
	
	
и получиться что-то вроде

	{* YouTube_PopUp *}
	<link rel="stylesheet" type="text/css" href="{THEME}/assets/youtubepopup/YouTubePopUp.css">
	<script type="text/javascript" src="{THEME}/assets/youtubepopup/YouTubePopUp.jquery.js"></script>
	<script type="text/javascript">
		$('a[href^="https://www.youtube.com/"]').addClass("bla-2");
		jQuery(function(){
		  jQuery("a.bla-1").YouTubePopUp();
		  jQuery("a.bla-2").YouTubePopUp( { autoplay: 0 } ); // Disable autoplay
		});
	</script>


### DEMO  для DLE
https://chuyakov.ru/#demoVideo 




# YouTube PopUp jQuery Plugin
jQuery plugin to display YouTube video or Vimeo video in PopUp, responsive &amp; retina, Compatible with WordPress, Autoplay support, easy to use.

##Live Demo

http://wp-time.com/youtube-popup-jquery-plugin/

##Usage

Easy to use, include jQuery and YouTubePopUp plugin and Style:

    <link rel="stylesheet" type="text/css" href="YouTubePopUp.css">
    <script type="text/javascript" src="jquery-1.12.1.min.js"></script>
    <script type="text/javascript" src="YouTubePopUp.jquery.js"></script>
    <script type="text/javascript">
      jQuery(function(){
          jQuery("a.bla-1").YouTubePopUp();
          jQuery("a.bla-2").YouTubePopUp( { autoplay: 0 } ); // Disable autoplay
      });
    </script>
  
Now add class to links, for example:

    YouTube:
    <a class="bla-1" href="https://www.youtube.com/watch?v=3qyhgV0Zew0">With Autoplay</a>
    <a class="bla-2" href="https://www.youtube.com/watch?v=3qyhgV0Zew0">Without Autoplay</a>
 
    Vimeo:
    <a class="bla-1" href="https://vimeo.com/81527238">With Autoplay</a>
    <a class="bla-2" href="https://vimeo.com/81527238">Without Autoplay</a>

For WordPress use Video PopUp plugin: http://wp-time.com/video-popup-plugin-for-wordpress/

Enjoy.

YouTubePopUp.js Plugin and Style by Qassim Hassan: https://twitter.com/QQQHZ

WP Time: http://wp-time.com
