<template>

  <telegram-passport
    :authParameters="{
      bot_id: 123456789,
      scope: ['id_document', 'address_document', 'phone_number', 'email'],
      public_key: 'Your public key',
      payload: 'Bot-specified payload',
    }"
  />
</template>

<script>
import {vueTelegramPassport} from 'vue-telegram-passport'

export default {
  name: 'your-component',
  components: {vueTelegramPassport},
}
</script>
