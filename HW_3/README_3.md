# GANs-HomeWork

Результат работы DCGAN после 10 эпох обучения:  
<p><img src="./pic_examples/dcgan.png"></p>

Для CSPGAN долго не удавалось добиться сходимости и хоть каких-то результатов, генератор выдавал что-то подобное прикрепленной ниже картинке постоянно (какие-то пиксельные рисунки различных форм и цветов). Я предполагаю, что мы попадали в ситуацию, когда генератор обманывал дискриминатор, при этом генерировав картинки, мягко говоря, совсем не из распределения лиц:
<p><img src="./pic_examples/csp_gan_avg.png"></p>

После увеличения скорости обучения для дискриминатора модель начала генерировать что-то более осмысленное (представлены скриншоты промежуточных стадий обучения):
<p><img src="./pic_examples/csp_gan_1.png"></p>
<p><img src="./pic_examples/csp_gan_2.png"></p>
<p><img src="./pic_examples/csp_gan_3.png"></p>

Уже что-то, а не просто шум и специфические пиксель арты, однако на второй и третьей картинках уже можно заметить, что наблюдается что-то похожее на модколлапс. В ноутбуке представлена визуализация работы модели, к сожалению, качество генерации оставляет желать лучшего, но хотя бы что-то похожее на лица (правда из фильмов ужасов, но это мелочи).