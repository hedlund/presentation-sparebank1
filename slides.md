# Sparebank 1

Front-end Architecture



## TODO

Whatevs


## Loosly inspired by Spotify

Teams are squads
Guilds for front-end (FFE), UX, design
Tribes?




## Felles Front-End (FFE)

![FFE screenshot](img/ffe.png)


Foxus on UI elements.
Previously only styling (Less)
Now also react components, such as
button, accordion, checkbox, date picker, dropdown, expandable, SVG icons, radio buttons, message boxes.

Focos on similar look and feel - UI, UX & UU.

## Nettbank Front-End (NFE)

Mix of UI elements and reusable good to haves

error logging, fetch wrapper & proxies (CSRF, error redirect, URL prefixer), session timeout, hash, i18n, form, validator, if, test tools.

## Kredittkort (KK)

Shared protypes
i18n
Various forms & UI elements



## Example button markup

```html
<button class="ffe-primary-button ffe-primary-button--loading">
  <span class="ffe-primary-button__label">
    <span class="ffe-primary-button__label-text">
      Yolo
    </span>
    <span class="ffe-primary-button__label-spinner">
      Loading...
    </span>
  </span>
</button>
```


## Self service portal

TBD

## Tech

Backbone, Handlebars, etc
Gulp


## Tools

* Nexus - both for `mvn` & `npm`
* Bitbucket Server (Stash)
* Jenkins
* Docker, docker, docker
* 'bob'


## bob

```
bob feature begin dig-666_a_good_name_for_a_branch
bob docker dnsgen start
bob release cherry-pick 1.2.0
```

https://github.com/jderusse/docker-dns-gen

## Yeoman

screenshot



## SB1 Kredittkort

Webpack
React
Redux
Webpack
  json-loader, less-loader
ImmutableJS
React Router & React Redux Router

Express + webpack-hot-middleware

npm as a build runner (other projects still use Gulp)


## Sparebank 1 Design System

* Built automatically from the React components
  * Uses the
* Node + Webpack + Handlebars


## Forms & validation

Evaluated redux-forms and revalidate
I wrote our packages nfe-form & nfe-validator
We've looked at reselect, but for now are using our own memoization implementation


## Visual Regression Testing

Gemini + Firefox running in a Docker instance

http://gemini-testing.github.io/gemini/



## Testing

Mocha + Chai
Sinon
Enzyme
Istanbul
Fitnesse


## Fitnesse

```
!include -c . FunksjonellTest.PageObject.TransaksjonerSide

!2 Gå til forside
!|script|sb1 browser test |
| Gå til forside          |

!3 Mål trafikk
-!| query: sjekk wiremock soap requests | $WIREMOCK    |
| kall                                  |versjon|antall|
| getCustomer                           | 3     | 1    |
```

```
!***> Gå til forside
!|scenario        | Gå til forside                |
|open             | ${HOST}/forside               |
|wait for visible | css=.card-overview            |
|show             | location                      |
|show             | take screenshot | forside.png |
```
hsac-fitnesse-fixtures + wiremock
