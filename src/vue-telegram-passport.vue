<template>
  <div id="telegram"></div>
</template>

<script>
export default {
  name: 'vue-telegram-passport',
  props: {
    authParameters: {
      type: Object,
      required: true,
      validator (value) {
        const required_fields =  ['bot_id', 'scope', 'public_key', 'payload']
        const isValid = required_fields.every(key => Object.keys(value).includes(key))
        if (!isValid) {console.error(`You must provide required fields: ${required_fields}`)}
        return isValid
      },
    },
    authButtonOptions: {
      type: Object,
      default () { return {} }
    }
  },
  mounted () {
    const telegramElement = document.getElementById('telegram')

    // create script with given params
    const script = document.createElement('script')
    script.src = 'https://raw.githack.com/TelegramMessenger/TGPassportJsSDK/master/telegram-passport.js'
    telegramElement.appendChild(script)

    script.onload = () => {
      Telegram.Passport.createAuthButton(
        telegramElement,
        this.authParameters,
        this.authButtonOptions,
      )
    }
  }
}
</script>
