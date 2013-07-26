imagefly
========

Componente Yii que gera thumbnails de acordo com a necessidade de tamanho.

##Requirements

Yii 1.1 or above.

##Instalation
1. Unzip the file inside the extension folder.

2. Add to your config / main.php the following line:
~~~
'import' => array (
   ...
   'application.extensions.ImageFly.components.*'
   ...
);
~~~

##Usage
~~~
//Normal mode
<img src='<?php echo ImageFly::Instance()->get($model, 'attr', Image::MEDIUM, Image::MEDIUM);?>'/>
---
<img src='<?php echo ImageFly::Instance()->get($model, 'attr', Image::MEDIUM);?>'/>
---
<img src='<?php echo ImageFly::Instance()->get($model, 'attr', 600, 745);?>'/>

//Using Chtml
echo CHtml::image(ImageFly::Instance()->get($model, 'attr', $x, $y));
~~~

##Models
Your model should have the following attributes
~~~
$model->imagePath
$model->imagePathThumb
~~~

Where the attribute ImagePath is the path of the original image
and imagePathThumb is the path where the thumbnail will be created.

eg:
~~~
public $imagePath = 'user/';
public $imagePathThumb = 'user/thumb/';
~~~
