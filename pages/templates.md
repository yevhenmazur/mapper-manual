---
title: Підложки; введення
authors:
  - Peter Hoban
  - Thomas Schoeps
  - Yevhen Mazur
keywords: Підложки
edited: 05 лютого 2016
---

<p>Зображення, треки з GPS приймачів а також інші матеріали, що використовуються в якості основи для спортивної карти називаються підложками. Вони можуть бути підключені до файлу карти за допомогою вікна параметрів підложок, що доступне через меню Підложки -&gt; Вікно параметрів підложок. Підложки також можуть використовуватись "не за призначенням" щоб зобразити певну інформацію на кінцевій карті, наприклад логотип спонсора, який доступний виключно у растровому форматі.</p>

<p><b>Увага</b>: Оскільки операції відмінити/повернути не поширюються на підложки, переконайтеся що зберегли файл перед тим як правити їх!</p>

<a name="types"><h4>Типи підложок</h4></a>
<p>OpenOrienteering Mapper дозволяє підключити у якості підложок файли таких форматів:</p>
<ul>
<li><a href="#type_image">Зображення</a>: bmp, jpg, png, tif, gif files</li>
<li><a href="#type_track">Треки</a>: dxf, gpx, osm files</li>
<li><a href="#type_map">Карти</a>: omap, ocd files</li>
</ul>

<p>Додатково, підложки можна розділити на <b>геоприв'язані</b> та <b>негеоприв'язані</b>. Для геоприв'язаних підложок доступна інформація щодо їх точного позицонування у відомій системі світових координат - див. <a href="georeferencing.md">геоприв'язка</a>. Таким чином, вони можуть бути автоматично позиціоновані на карті, за умови що карта також є геоприв'язаною. Для негеоприв'язаних підложок, ця інформація недоступна, тому їх доведеться <a href="#positioning">позиціонувати вручну</a>.

<a name="setup"><h4>Вікно параметрів підложок</h4></a>

<br/><br/><img src="images/template_setup_window.png" border="0" /><br/><br/>

<p>Це вікно відкривається через пункт меню Підложки -&gt; Вікно параметрів підложок. У його центральній частині знаходиться список усіх відкритих підложок. Шар з самою картою також показаний тут. Послідовність елементів у цьому списку визначає порядок у якому вони будуть відтворені: перший буде з самого верху, останній - внизу.</p>

<p>Кожен елемент може бути прихований або показаний за допомогою флажка у лівій частині. Крім цього, є можливість керувати прозорістю кожного шару, задаюи відсоток непрозорості.</p>

<h4 id="open">Відкриття підложки</h4>
<p>Клацніть на кнопку "Додати підложку..." у вікні параметрів підложок і виберіть файл що має бути підключений як підложка. Див. <a href="#types">типи підложок</a> щоб дізнатися про всі підтримувані формати файлів.</p>

<h4 id="draw_order">Зміна порядку відтворення підложок</h4>
<p>Коли підложка вибрана, її можна рухати вверх або вниз по списку за допомогою кнопок Підняти/Опустити, це також зміню порядок у якому вона буде відтворена.</p>

<h4 id="close">Видалення або закриття підложки</h4>
<p>Використовуючи кнопку Видалити або Закрити, можна відключити підложку. Назва кнопки залежить від <a href="settings.md#keep_closed_templates">відповідної настройки</a> "запам'ятовувати налаштування закритих підложок": якщо вона активна, кнопка буде позначена як "Закрити" і залишиться можливість повторно відкрити підложку за допомогою пункту меню Підложки -&gt; Відкрити підложку знову..., у іншому випадку це буде "Видалити" без можливості повторно відкривати підложку в майбутньому.</p>

<h4 id="positioning">Positioning</h4>
<p>At the bottom of the window, there are the template positioning capabilities:</p>

<p>The upper left button shows whether the template is <b>georeferenced</b>. Later it may become possible to switch the georeferencing setting using this button, but this is not yet implemented.</p>

<p>At the lower left is the <b>Move by hand</b> button. It allows to move non-georeferenced templates by clicking in the map display and dragging the mouse.</p>

<p>At the lower right is the toggle for the <b>template positioning window</b>. It enables to enter numerical values for the positioning of non-georeferenced templates, e.g. to rotate a template by 90 degrees, or to adapt the template rotation to the magnetic declination.</p>

<p><a name="adjust">At the upper right is the <b>Adjust</b> button which enables to adjust the position of a non-georeferenced template to that of an existing template, or the map, which is in the correct position already.</a> <a href="template_adjust.md">Detailed instructions here</a>.</p>


<h4>Template types</h4>

<a name="type_image"><h3>Image templates</h3></a>

<p>Raster images are loaded as this template type. When opening such a template, the image positioning dialog is shown:</p>

<br/><br/><img src="images/template_image_positioning.png" border="0" /><br/><br/>

<h4>Georeferenced positioning</h4>

<p>This option is only available if the image has georeferencing information associated. OpenOrienteering supports this via so-called world files. A world file for an image must have the same file name as the image file and be in the same directory. The world file extension is determined by the image extension: it consists of the first character of the image file extension, then the last character of this extension, and then the letter w. For example, a world file for a bmp file would have the extension bpw, or for tiff it would be tfw. Alternatively, the world file extension can also be wld.</p>

<p>World files are text files containing 6 entries of a transformation matrix mapping pixel coordinates to grid coordinates of some geodesic coordinate reference system (<a href="http://en.wikipedia.org/wiki/World_file">more information on Wikipedia</a>). Unfortunately, they do not specify which coordinate reference system it is. So if you choose this option for positioning, you have to specify the coordinate reference system in the next step. You should get this information from the place where you got the georeferenced image from. For example, in Germany it is usually UTM or Gauss-Kr&uuml;ger with a limited range of possible middle meridians.</p>

<p>In order for georeferenced positioning to work, the map must be georeferenced, too. If it is not at this point in time, the <a href="georeferencing.md">map georeferencing dialog</a> is shown as the next step, with the reference point coordinates already pre-filled as the center of the loaded image.</p>

<h4>Manual positioning</h4>

<p>This method of positioning should only be chosen if you have no georeferencing information available for the image. First, there are two possible options to specify the image scale:</p>

<ul>
<li><b>Meters per pixel</b>: this is primarily useful for base maps from a digital source, where you may know this value directly. Alternatively you can also calculate it yourself: if your fieldwork image covers 500m width on the ground and the image is 1200 pixels wide then the scale will be 500 / 1200 = 0.625 metres per pixel. (Take care that the number of metres corresponds exactly the width of the image file.)</li>
<li><b>Scanned</b>: if your fieldwork is at a known scale (it should be &#8212; say 1:5000), and the scan is at a chosen resolution (say 200dpi) then these parameters may be entered to scale the fieldwork image. This assumes that printer and scanner work accurately.</li>
</ul>

<p>Note that if you do not know the image scale and / or if you are going to adjust the template position to the existing map anyway using the <a href="#adjust">adjust feature</a>, you can just enter any value here as the scaling will be changed again later.</p>

<a name="type_track"><h3>Track templates</h3></a>

<p>These templates can be tracks from a GPS receiver (including waypoints) or vector graphics such as dxf files. For the latter, you have to select a coordinate reference system when loading the file. If it is just a drawing which is not georeferenced, select the option "Local" so will not be distorted.</p>

<a name="type_map"><h3>Map templates</h3></a>

<p>This template type enables to load other map files as a template. This has two main purposes:</p>

<ul>
<li>Loading an old orienteering map as a base map for a new one.</li>
<li>Loading a map as a base layer to set a course on top of it.</li>
</ul>

<p>For now, map templates can only be loaded as non-georeferenced.</p>

