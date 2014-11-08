yii2-widget-activeform
======================
Extends and enhances the [Yii ActiveForm widget](https://github.com/yiisoft/yii2/blob/master/framework/widgets/ActiveForm.php). Facilitates all [three form layouts](http://getbootstrap.com/css/#forms-example) available in Bootstrap i.e. __vertical__, __horizontal__, and __inline__. Allows options for offsetting labels and inputs for horizontal form layout. Works closely with the extended ActiveField widget. In addition, this extension enhances and extends the [Yii ActiveField widget](https://github.com/yiisoft/yii2/blob/master/framework/widgets/ActiveField.php). Allows Bootstrap styled [input group addons](http://getbootstrap.com/components/#input-groups-basic) to be prepended or appended to textInputs. Automatically adjusts checkboxes and radio input offsets for horizontal forms. Allows, flexibility to control the labels and placeholders based on form layout style (e.g. hide labels and show them as placeholder for inline forms). The extended ActiveField functionalities available are:

- Addons
	* Prepend Addon
	* Append Addon
	* Icon Addon
	* Input Addon
	* Button Addon
	* Button Dropdown Addon
	* Segmented Button Addon
	* Prepend & Append
	* Input Group Settings
- Inputs
	* Checkbox
	* Radio
	* Checkbox List
	* Radio List
	* Static Input
	* HTML 5 Input
- Multi Select
	* Vertical Form
	* Horizontal Form
	* Radio List
	* Display Options

> NOTE: This extension is a sub repo split of [yii2-widgets](https://github.com/kartik-v/yii2-widgets). The split has been done since 08-Nov-2014 to allow developers to install this specific widget in isolation if needed. One can also use the extension the previous way with the whole suite of [yii2-widgets](http://demos.krajee.com/widgets).

## Installation

The preferred way to install this extension is through [composer](http://getcomposer.org/download/). Check the [composer.json](https://github.com/kartik-v/yii2-widget-activeform/blob/master/composer.json) for this extension's requirements and dependencies. Read this [web tip /wiki](http://webtips.krajee.com/setting-composer-minimum-stability-application/) on setting the `minimum-stability` settings for your application's composer.json.

To install, either run

```
$ php composer.phar require kartik-v/yii2-widget-activeform "*"
```

or add

```
"kartik-v/yii2-widget-activeform": "*"
```

to the ```require``` section of your `composer.json` file.

## Latest Release

> NOTE: The latest version of the module is v1.0.0 released on 08-Nov-2014. Refer the [CHANGE LOG](https://github.com/kartik-v/yii2-widget-activeform/blob/master/CHANGE.md) for details.

### Demo

You can refer detailed documentation and demos for [ActiveForm](http://demos.krajee.com/widget-details/active-form) or [ActiveField](http://demos.krajee.com/widget-details/active-field) for understanding the usage of the extension.

### Usage

#### ActiveForm

```php
// add this in your view
use kartik\widgets\ActiveForm;

// Vertical Form
$form = ActiveForm::begin([
'id' => 'form-signup',
'type' => ActiveForm::TYPE_VERTICAL
]);

// Inline Form
$form = ActiveForm::begin([
'id' => 'form-login', 
'type' => ActiveForm::TYPE_INLINE,
'fieldConfig' => ['autoPlaceholder'=>true]
]);

// Horizontal Form Configuration
$form = ActiveForm::begin([
'id' => 'form-signup', 
'type' => ActiveForm::TYPE_HORIZONTAL,
'formConfig' => ['labelSpan' => 3, 'deviceSize' => ActiveForm::SIZE_SMALL]
]);
```

#### ActiveField
```php
// Prepend an addon text
echo $form->field($model, 'email', ['addon' => ['prepend' => ['content'=>'@']]]);

// Append an addon text
echo $form->field($model, 'amount_paid', [
    'addon' => ['append' => ['content'=>'.00']]
]);

// Formatted addons (like icons)
echo $form->field($model, 'phone', [
    'addon' => [
        'prepend' => [
            'content' => '<i class="glyphicon glyphicon-phone"></i>'
        ]
    ]
]);

// Formatted addons (inputs)
echo $form->field($model, 'phone', [
    'addon' => [
        'prepend' => [
            'content' => '<input type="radio">'
        ]
    ]
]);

// Formatted addons (buttons)
echo $form->field($model, 'phone', [
    'addon' => [
        'prepend' => [
            'content' => Html::button('Go', ['class'=>'btn btn-primary'])
        ]
        'asButton' => true
    ]
]);
```
## License

**yii2-widget-activeform** is released under the BSD 3-Clause License. See the bundled `LICENSE.md` for details.