---
layout: default
group: arch-guide
subgroup: Architectural Layers
title: Magento Themes
menu_title: Magento Themes
menu_order: 1
version: 2.0
github_link: architecture/archi_perspectives/themes_intro.md
redirect_from: /guides/v1.0/architecture/archi_perspectives/themes_intro.html
---

## Introduction

A {% glossarytooltip d2093e4a-2b71-48a3-99b7-b32af7158019 %}theme{% endglossarytooltip %} is a component of Magento application that provides a consistent look and feel (visual design) for entire application area (for example, {% glossarytooltip 1a70d3ac-6bd9-475a-8937-5f80ca785c14 %}storefront{% endglossarytooltip %} or Magento admin) using a combination of custom templates, layouts, styles or images.

Out-of-the-box Magento application provides two design themes: Luma, as a demonstration theme, and Blank as a basis for custom theme creation.

All theme files are stored under `app/design/<area>/<Vendor>/<theme>/`.

Apart from the configuration file and theme {% glossarytooltip 3f0f2ef1-ad38-41c6-bd1e-390daaa71d76 %}metadata{% endglossarytooltip %} file, all theme files fall into the following two categories:

* Static view files are a set of theme files that are returned by the server to a browser as is, without any processing, are called the {% glossarytooltip 363662cb-73f1-4347-a15e-2d2adabeb0c2 %}static files{% endglossarytooltip %} of a theme.

* Dynamic view files are view files that are processed or executed by the server in order to provide result to the client.
  These are: .less files, templates, layouts .

Design packets are collections of related themes plus nondefault variants.


Magento supports multi theme model.
Themes are highly extensible.

## Control

1) The visual aspect of site design (skinning).
Includes CSS, images, design/UI- specific {% glossarytooltip 312b4baf-15f7-4968-944e-c814d53de218 %}Javascript{% endglossarytooltip %}

2) Many functional aspects of site.
    **Layouts** control which default blocks/modules are available.
    **Templates** control which data is shown on page.

## Theme components

Magento theme components include:

* Layout:  {% glossarytooltip 73ab5daa-5857-4039-97df-11269b626134 %}layout{% endglossarytooltip %} {% glossarytooltip 8c0645c5-aa6b-4a52-8266-5659a8b9d079 %}XML{% endglossarytooltip %} files.
This defines which template file to load.

* Template: template files which are generally .phtml files.

* Skin: static files like images, {% glossarytooltip 6c5cb4e9-9197-46f2-ba79-6147d9bfe66d %}css{% endglossarytooltip %} and js.

* Locale: language related file.
This will be used when you want to make your theme compatible with different languages.

## Theme process flow

### Process flow

In general Magento's fallback technique for theme is as below:

Your Custom Package >> Default Package >> Base Package >> Error Message

From above hierarchy you can imagine that if any of the requested file is not available in your theme then it will look for default package first and after that look into Base package and at last it will show error message if requested file is not available in any of the package.

Theme inheritance  based on the fallback mechanism, which guarantees that if a view file is not found in the current theme, the system searches in the ancestor themes, {% glossarytooltip c1e4242b-1f1a-44c3-9d72-1d5b1435e142 %}module{% endglossarytooltip %} view files or {% glossarytooltip 08968dbb-2eeb-45c7-ae95-ffca228a7575 %}library{% endglossarytooltip %}

* page templates
* block templates
* layouts

Apart from the configuration file and theme metadata file, all theme files fall into the following two categories:

*	Static view files.
  These theme files are returned by the server to a browser as is, without any processing, and are called the static files of a theme.

*	Dynamic view files.
  View files that are processed or executed by the server in order to provide result to the client.
  These are: .less files, templates, layouts

### Where do themes live?

Each theme resides in a unique directory under `app/design/frontend` or `app/design/adminhtml` folder.
This directory contains page templates and layouts for Magento modules.

The base package provides hooks to all of Magento's core features.

We recommend you add override features rather than edit default theme files.

<h2 id="related">Related topics</h2>
<a href="{{page.baseurl}}architecture/archi_perspectives/arch_diagrams.html">Architectural diagrams</a>