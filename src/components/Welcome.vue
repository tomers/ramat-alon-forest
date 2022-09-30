<template>
  <div class="bg-white q-pa-sm">
    <div class="row justify-center">
      <q-btn
        icon="navigation"
        label="לניווט ביער"
        color="red-9"
        size="lg"
        padding="xs xl"
        glossy
        stack
        @click="onClick"
      />
    </div>
    <q-img src="welcome.jpg" />
    <div class="text-center text-primary">
      <div class="text-h5 text-bold">
        <div>
          צוות יער רמת אלון
        </div>
        <div>
          מודה לכם שבאתם לטייל
        </div>
        <div>
          בפינת החמד אותה אנחנו מטפחים
        </div>
      </div>
      <div>
        אנו מקווים שתהנו מהיער שלנו
      </div>
      <div>
        ותעזרו לשמור על נקיונו ועל הטבע הקיים בו
      </div>
    </div>
  </div>
</template>

<script>
import { openURL } from 'quasar'
import Globals from 'src/globals'

export default {
  setup () {
    return {}
  },

  methods: {
    onClick () {
      openURL(Globals.map_url)
    }
  }
}
</script>
