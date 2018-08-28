<h1>Vue Telegram Passport</h1>
<p>
    <img src="https://i.imgur.com/9NBqALW.png" />
    <br>
    <br>
    <a href="https://badge.fury.io/js/vue-telegram-passport">
        <img src="https://badge.fury.io/js/vue-telegram-passport.svg" />
    </a>
    <a href="https://www.npmjs.com/package/vue-telegram-passport">
        <img src="https://img.shields.io/npm/dm/vue-telegram-passport.svg" />
    </a>
    <a href="https://travis-ci.org/vchaptsev/vue-telegram-passport">
        <img src="https://travis-ci.org/vchaptsev/vue-telegram-passport.svg?branch=master" />
    </a><br>
</p>

**vue-telegram-passport** is a Vue component for [Telegram Passport](https://telegram.org/blog/passport)


## Installation

Install with [npm](https://npmjs.com):

  ```bash
  $ npm i vue-telegram-passport
  ```

Install with [yarn](https://yarnpkg.com):

  ```bash
  $ yarn add vue-telegram-passport
  ```

or if you just want to try it out, [unpkg](https://unpkg.com/#/) has ready-to-use packages.

```html
<script src="https://unpkg.com/vue"></script>
<script src="https://unpkg.com/vue-telegram-passport"></script>
```
## Usage

Import `vue-telegram-passport`, pass it to the `components` and use in your template

```html
<template>
  ...
  <vueTelegramPassport
    :authParameters="{
      bot_id: 123456789,
      scope: ['id_document', 'address_document', 'phone_number', 'email'],
      public_key: 'Your public key',
      nonce: 'Bot-specified payload',
    }"/>
    ...
</template>

<script>
import {vueTelegramPassport} from 'vue-telegram-passport'

export default {
  ...
  components: vueTelegramPassport,
  ...
}
</script>
```


## Props
You can play around with options on the official [passport page](https://core.telegram.org/passport/example)

| Name              | Description                                                                   | Required | Default     |
| ----------------- | ----------------------------------------------------------------------------- | -------- | ----------- |
| authParameters    | [docs](https://core.telegram.org/passport/sdk-javascript#authparameters)      | True     | null        |
| authButtonOptions | [docs](https://core.telegram.org/passport/sdk-javascript#authbuttonoptions)   | False    | {}          |


## Links
+ [Official blog post](https://telegram.org/blog/passport) – basic description and examples
+ [Official docs](https://core.telegram.org/passport) – bot preparation instructions
+ [Official JS SDK docs](https://core.telegram.org/passport/sdk-javascript) – fields, options descriptions
