# Superpeer Task (Vue)

This project tries to solve the task on https://kodilan.com/ilanlar/superpeer-ui-developer

## Demo

You can check the result on both desktop and mobile devices by visiting http://superpeertaskvue.test.rebootworks.com/

## Classic HTML Version

You can check the classic HTML version by visiting https://github.com/hayatbiralem/superpeer-task/

## Usage

```
git clone git@github.com:hayatbiralem/superpeer-task.git
cd superpeer-task
yarn install
yarn dev
```

And then visit http://localhost:1234/

To build project you can use `yarn build` command.

## SVG Sprite Generation

You can always use [icomoon.io](https://icomoon.io/app) to manage your svg icons which is very useful but we have a local solution eather.

You can add/remove your svg icons to/from `src/static/icons` folder and then run following command to regenerate svg sprite.

```
npm install svg-sprite -g
yarn svgsprite
```

It will update `src/static/sprite/icons.svg` file contents as a svg sprite. You can copy/paste its contents to between the `<template></template>` tag in the `SvgSprite.vue` file.

## Points I care about

- I used Parcel to package things.
- I used [InuitCSS Architecture](https://github.com/inuitcss/inuitcss) based on ITCSS and BEM Methodology. Probably you know that but this is not a CSS Framework like Bootstrap. It does not contain any cosmetics.
- I used comments to make things clear in HTML and CSS.
- I tried to use semantic syntax and accessibility attributes.
- I used inline SVG sprite.
- I tried to achieve pixel perfect by using screenshots as layers in Photoshop. See the [pixel-perfect.png](pixel-perfect.png) file.
- I used responsive images.
- I made sure that the real mobile experience can be tested at widths of 479px and below.
- I used mobile first approach.
- I checked Chrome, Firefox, Opera, Edge, IE11, iOS Safari/Chrome, Android Default/Chrome browsers.
- I fixed the select apperance issue at IE11.
- I fixed the iOS Safari input zoom problem caused by the input size being 15px (below 16px) and I made a SASS mixin for it.
- I couldn't solve the text ellipsis issue at select elements on IE11 with only CSS but I could with some Javascript by following [this approach](https://nikitahl.com/text-overflow-ellipsis-on-select-tag/).
- I tried to make usefull Vue components.
- I sent simple closure functions to the buttons via VueJS.
- I fixed `Object doesn't support property or method 'assign'` error on IE11 by using related pollyfill.

## My Qualifications

- I love CSS, Math and solving problems.
- I've been coding CSS since 2010.
- I also know NodeJS, PHP, Laravel, WordPress, bash and servers... In short I know back-end stuff.
- I'm good at reading and writing in English. I've been talking to Cambly teachers for two years now (you can verify that by following [this link](https://www.cambly.com/en/certificate/verify/f8478219)), so I'm good at listening and speaking too. I am comfortable in daily conversations but I must say that my vocabulary and grammar are poor.

## TODO

- [ ] Genereta sprite icons via Parcel/WebPack.
