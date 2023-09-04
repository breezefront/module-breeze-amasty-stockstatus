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

## Installation

```bash
composer require swissup/module-breeze-amasty-stockstatus
bin/magento setup:upgrade --safe-mode=1
```
