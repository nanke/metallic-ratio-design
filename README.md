[![version][version-badge]][CHANGELOG] [![license][license-badge]][LICENSE]

# Mettalic Ratio Design

## Introduction
This projects aim to create a simple generator for a stylesheet that allows to upgrade layouts by controlling visual components dimensions.

## Install

```sh
npm install metallic-ratio-design
```

## About

### Metallic Ratios

[Metallic ratios](https://en.wikipedia.org/wiki/Metallic_mean) (means) are simply ratios obtained by computing the limit of the ratio between natural numbers that 

## Usage

### Components

The idea is to identify whether we want the "little" component (a), its "medium" counterpart (b), and/or the gutter (g). When grabbing two or more components (ab, nb, or anb) the gutter between them is accounted for. To get the size of the remainder we can account for all gutter (an-1bxs or nbxs).

### Classes

The mettalic ratio classes can be combined in many ways.
The most specific format contains the following details:

`e.g.: .mrd-w-sm-gold-a`

1. Dimension(s) (one of):
    * "w" (width/columns)
    * "h" (height/rows) 
    * "wh" (both)
2. Screen size (one of):
    * "xs" (extra small : < 544px)
    * "sm" (small : >= 544px)
    * "md" (medium : >= 768px)
    * "lg" (large : >= 992px)
    * "xl" (extra large : >= 1200px)
3. Ratio (Index): From 1 to N where:
    * gold === 1
    * silver === 2
    * bronze === 3
    * copper === 4
    * nickel === 5
    * tin === 6
4. Fraction (one of):
    * a : "little" component
    * ag : "little" component plus one gutter
    * ab : "little" and **one** "medium" component with gutter in between
    * abg : "little" and **one** "medium" component with gutter in between plus one extra gutter
    * ab2g : "little" and **one** "medium" component with gutter in between plus two gutters
    * an-1b : "little" and **all but one** "medium" component with gutter in between
    * an-1bg : "little" and **all but one** "medium" component with gutter in between plus one gutter
    * an-1b2g : *all but one** "medium" component
    * anb: **all but two** gutters
    * anbg: **all but one** gutter
    * b : "medium" component
    * bg : "medium" component plus one gutter
    * nb : **all** "medium" component with gutter in between
    * nbg : **all** "medium" component with gutter in between plus one extra gutter
    * nb2g : **all but** "little" component


### Equivalent styles

Here are all the ways to make a component respond to the same style:
* For the width only
* For small screen sizes
* For the a (little) component (no gutter)
* Using the golden (first) ratio

```css
/** Most specific above **/
.mrd-w-sm-gold-a
.mrd-w-sm-1-a
.mrd-w-sm-gold > .mrd-a
.mrd-w-sm-1 > .mrd-a
.mrd-w-sm > .mrd-gold-a
.mrd-w-sm > .mrd-1-a
.mrd-w-sm .mrd-gold > .mrd-a
.mrd-w-sm .mrd-1 > .mrd-a
.mrd-w .mrd-sm-gold-a
.mrd-w .mrd-sm-1-a
.mrd-w .mrd-sm-gold > .mrd-a
.mrd-w .mrd-sm-1 > .mrd-a
.mrd-w .mrd-sm > .mrd-gold-a
.mrd-w .mrd-sm > .mrd-1-a
.mrd-w .mrd-sm .mrd-gold > .mrd-a
.mrd-w .mrd-sm .mrd-1 > .mrd-a
/** Least specific below **/
```