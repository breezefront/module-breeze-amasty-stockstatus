# Custom Stock Status by Amasty Breeze Frontend Integration

## Required patches

`vendor/amasty/stockstatus/view/frontend/web/js/amstockstatus.js`

Find the code in the `_reloadContent` method:

```js
    this.nodes.spanElement.replaceWith(this.options[key]['custom_status']);
```

and add the following line after it:

```js
    this.nodes.spanElement = $(this.selectors.stock).first();
```

Find the code:

```js
this.nodes.stockAlertElement = $('<div>', {
    class: this.classes.stockAlert,
    'data-amstock-js': 'alert',
    title: $t('Subscribe to back in stock notification'),
    rel: 'external'
});
```

and replace it with:

```js
this.nodes.stockAlertElement = $('<div>')
    .addClass(this.classes.stockAlert)
    .attr('data-amstock-js', 'alert')
    .attr('title', $t('Subscribe to back in stock notification'))
    .attr('rel', 'external');
```

## Installation

```bash
composer require swissup/module-breeze-amasty-stockstatus
bin/magento setup:upgrade --safe-mode=1
```
