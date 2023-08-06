# GANs-HomeWork
### Попытка покадровой дорисовки с помощью MAT

Веса Celeba:
<p><img src="./pics_and_gifs/big_celeba.gif"\></p>

Веса FFHQ:
<p><img src="./pics_and_gifs/big_ffhq.gif"\></p>

### Эксперименты с меньшими масками на одной фотографии:

Оригинал:
<p><img src="./pics_and_gifs/cropped_original.png"\></p>

Маски №1 и №2:
<p><img src="./pics_and_gifs/img_0_small_mask.png"\></p>
<p><img src="./pics_and_gifs/img_1_bigger_mask.png"\></p>

Восстановление от MAT (веса CelebA):
<p><img src="./pics_and_gifs/img_0_CelebA.png"\></p>
<p><img src="./pics_and_gifs/img_1_CelebA.png"\></p>

Восстановление от MAT (веса FFHQ):
<p><img src="./pics_and_gifs/img_0_FFHQ.png"\></p>
<p><img src="./pics_and_gifs/img_1_FFHQ.png"\></p>

Восстановление от GPEN:
<p><img src="./pics_and_gifs/img_0_GPEN.jpg" height="512px"\></p>
<p><img src="./pics_and_gifs/img_1_GPEN.jpg" height="512px"\></p>

Восстановление от MAT (веса FFHQ) кажется несколько лучше, чем MAT (веса CelebA), и значительно лучше, чем GPEN, поэтому дальнейшие эксперименты было решено проводить с фотографией, восстановленной MAT (веса FFHQ).

Улучшение от GPEN после восстановление MAT (веса FFHQ):
<p><img src="./pics_and_gifs/img_0_FFHQ_GPEN.jpg" height="512px"\></p>

Картинка стала красивее, более яркой, увеличилось разрешение, немного добавился макияж, но улучшение не затронуло недочеты предшествующего восстановления от MAT.

Замена лица от SimSwap:
<p><img src="./pics_and_gifs/result_whole_swapsingle.jpg" height="512px"\></p>

# Вывод:

На данный момент библиотека MAT не показывает заявленных результатов для инпэйнтинга или, по крайней мере, мне не удалось достичь подобных результатов, где закрыто маской более 80% лица и происходит качественное восстановление. В README показаны неудачные попытки покадрово восстановить видео с помощью MAT с весами моделей, натренированных на датасетах CelebA и FFHQ, а также небольщой пул экспериментов с восстановлением одной фотографии с масками меньшего размера при помощи библиотек MAT и GPEN и последующим улучшением от GPEN Enhancement, и пересадкой лица от SimSwap. Библиотека для пересадки лица показывает хорошее качество, учитывая, что мы пересаживали одно и тоже лицо, но с разных фотографий. Полученное изображение выглядит довольно хорошо, повторно улучшить его с помощью GPEN Enhancement не получилось из-за ошибки рантайма, по всей видимости библиотека всегда увеличивает входное разрешение изображения вне зависимости от исходного. Во второй раз на вход уже подавалось разрешение 2048x2048, а не 512x512 как в первый раз. В связи с этим, для дальнейшего улучшения полученных изображений предлагается использовать GPEN Enhancement после SimSwap, а не до.