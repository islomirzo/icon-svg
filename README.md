# icon-svg

<h3>This CSS trick allows you to use SVG images as icons</h3>

<h4>HTML</h4>

```html
<!-- Default -->
<i class="icon icon-face-smile"></i>
<i class="icon icon-face-wink"></i>

<!-- Sample with css color -->
<i class="icon icon-face-neutral" style="color: red;"></i>
<i class="icon icon-face-sad" style="color: red;"></i>

<!-- Sample with css size -->
<i class="icon icon-face-content"></i>
<i class="icon icon-face-happy"></i>
```

<h4>Scss</h4>

```scss
$path-icons: '../svg-icons';

// Icons list
$icons:
        'face-smile',
        'face-wink',
        'face-neutral',
        'face-sad',
        'face-content',
        'face-happy',
;

@mixin icon-size($size: 1rem) {
  width: $size;
  min-width: $size;
  height: $size;
  min-height: $size;
}

.icon {
  display: inline-block;
  mask-size: contain;
  -webkit-mask-size: contain;
  mask-position: center;
  -webkit-mask-position: center;
  mask-repeat: no-repeat;
  -webkit-mask-repeat: no-repeat;
  background-color: currentcolor;
  @include icon-size();
}

@each $icon in $icons {

  .icon-#{$icon} {
    mask-image: url("#{$path-icons}/#{$icon}.svg");
    -webkit-mask-image: url("#{$path-icons}/#{$icon}.svg");
  }
}
```
