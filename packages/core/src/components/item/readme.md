# ion-item

Items are elements that can contain text, icons, avatars, images, inputs, or anything else. Generally they are placed in a list with other items. Items can be swiped, deleted, reordered, edited, and more.


## Common Usage
There are a few elements that are considered items, but not all of them are styled to look the same.
The basic item can be written as an `<ion-item>` element or it can be added to any element by adding
`ion-item` as an attribute. List headers and item dividers, although styled differently, are also items
and can be written as `<ion-list-header>` and `<ion-item-divider>`, respectively.

### As an Element
A basic item should be written as a `<ion-item>` element when it is not clickable.

```html
<ion-item>
  Item
</ion-item>
```

A list header should be written as `<ion-list-header>`.

```html
<ion-list-header>
  List Header
</ion-list-header>
```

An item divider should be written as `<ion-item-divider>`.

```html
<ion-item-divider>
  Item Divider
</ion-item-divider>
```

### As an Attribute
The attribute `ion-item` should be added to a `<button>` when the item can be clicked or tapped. It
should be added to an `<a>` element when the item needs to contain a `href`. It can be added as an
attribute to any element to take on the item styling.

```html
<button ion-item (click)="buttonClick()">
  Button Item
</button>

<a ion-item href="https://www.ionicframework.com">
  Anchor Item
</a>
```

Note: do not add `ion-item` as an attribute to an `<ion-list-header>` or `<ion-item-divider>` element
as they are already items and their styling will be changed to look like a basic item.

## Detail Arrows
By default, `<button>` and `<a>` elements with the `ion-item` attribute will display a right arrow icon
on `ios` mode. To hide the right arrow icon on either of these elements, add the `detail-none` attribute
to the item. To show the right arrow icon on an element that doesn't display it naturally, add the
`detail-push` attribute to the item.

```html
<ion-item detail-push>
  Item with Detail Arrow
</ion-item>

<button ion-item (click)="buttonClick()">
  Button Item with Detail Arrow
</button>

<a ion-item detail-none href="https://www.ionicframework.com">
  Anchor Item with no Detail Arrow
</a>
```

This feature is not enabled by default for `md` and `wp` modes, but it can be enabled by setting the
Sass variables `$item-md-detail-push-show` and `$item-wp-detail-push-show`, respectively, to `true`.
It can also be disabled for ios by setting `$item-ios-detail-push-show` to `false`. See the
[theming documentation](http://ionicframework.com/docs/theming/overriding-ionic-variables/) for
more information on overriding Sass variables.


## Item Placement
Items rely heavily on content projection to position content. The item grabs content based on the
element or attribute and positions it that way. This logic makes it possible to write a complex
item with simple, understandable markup without having to worry about styling and positioning
the elements.

The below chart details the attributes item looks for and where it will place the element with
that attribute inside of the item:

| Attribute      | Description                                                                                          |
|----------------|----------------------------------------------------------------------------------------------------- |
| `item-start`   | Placed to the left of all other elements, outside of the inner item.                                 |
| `item-end`     | Placed to the right of all other elements, inside of the inner item, outside of the input wrapper.   |
| `item-content` | Placed to the right of any `ion-label`, inside of the input wrapper.                                 |

### Checkboxes, Radios and Toggles
[Checkboxes](../../checkbox/Checkbox) are positioned in the same place as the `item-start` attribute.
[Radios](../../radio/RadioButton) and [Toggles](../../toggle/Toggle) are positioned in the same place
as the `item-end` attribute. All of these components can be positioned differently by adding the
`item-start` or `item-end` attribute.

### Content and Inputs
A [Label](../../label/Label) is placed inside of the item to the left of all content and inputs. The
following components are all placed in the same position as the `item-content` attribute: [Select](../../select/Select),
[Input](../../input/Input), [TextArea](../../input/TextArea), [DateTime](../../datetime/DateTime), and
[Range](../../range/Range).

Any element directly placed inside of an `<ion-item>` that does not have one of the previously mentioned
attributes and isn't one of the above elements will be placed inside of a [Label](../../label/Label).

### Text Alignment
By default, Items will align text to the left and add an ellipsis when the text is wider than the item.
See the [Utility Attributes Documentation](../../../../theming/css-utilities/) for attributes that can
be added to `ion-item` to transform the text.

```html
<ion-list>

  <ion-list-header>
    Header
  </ion-list-header>

  <ion-item>
    Item
  </ion-item>

  <ion-item detail-push>
    Item with Detail Arrow
  </ion-item>

  <button ion-item (click)="buttonClick()">
    Button Item
  </button>

  <ion-item-divider>
    Item Divider
  </ion-item-divider>

  <button ion-item detail-none (click)="buttonClick()">
    Button Item with no Detail Arrow
  </button>

  <a ion-item href="https://www.ionicframework.com">
    Anchor Item
  </a>

  <ion-item no-lines>
    Item with no border
  </ion-item>

  <ion-item text-wrap>
    Multiline text that should wrap when it is too long
    to fit on one line in the item.
  </ion-item>

</ion-list>
```


<!-- Auto Generated Below -->


## Properties

#### color

string

The color to use from your Sass `$colors` map.
Default options are: `"primary"`, `"secondary"`, `"tertiary"`, `"success"`, `"warning"`, `"danger"`, `"light"`, `"medium"`, and `"dark"`.
For more information, see [Theming your App](/docs/theming/theming-your-app).


#### detail

boolean

If true, a detail arrow will appear on the item. Defaults to `false` unless the `mode`
is `ios` and an `href`, `onclick` or `tappable` property is present.


#### disabled

boolean

If true, the user cannot interact with the item. Defaults to `false`.


#### href

string

Contains a URL or a URL fragment that the hyperlink points to.
If this property is set, an anchor tag will be rendered.


#### mode



The mode determines which platform styles to use.
Possible values are: `"ios"` or `"md"`.
For more information, see [Platform Styles](/docs/theming/platform-specific-styles).


#### onclick



Callback function.
If this property is set, a button tag will be rendered.


#### tappable

boolean

Whether or not this item should be tappable.
If true, a button tag will be rendered. Defaults to `false`.


## Attributes

#### color

string

The color to use from your Sass `$colors` map.
Default options are: `"primary"`, `"secondary"`, `"tertiary"`, `"success"`, `"warning"`, `"danger"`, `"light"`, `"medium"`, and `"dark"`.
For more information, see [Theming your App](/docs/theming/theming-your-app).


#### detail

boolean

If true, a detail arrow will appear on the item. Defaults to `false` unless the `mode`
is `ios` and an `href`, `onclick` or `tappable` property is present.


#### disabled

boolean

If true, the user cannot interact with the item. Defaults to `false`.


#### href

string

Contains a URL or a URL fragment that the hyperlink points to.
If this property is set, an anchor tag will be rendered.


#### mode



The mode determines which platform styles to use.
Possible values are: `"ios"` or `"md"`.
For more information, see [Platform Styles](/docs/theming/platform-specific-styles).


#### onclick



Callback function.
If this property is set, a button tag will be rendered.


#### tappable

boolean

Whether or not this item should be tappable.
If true, a button tag will be rendered. Defaults to `false`.



----------------------------------------------

*Built with [StencilJS](https://stenciljs.com/)*
