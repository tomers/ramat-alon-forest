<template>
  <div class="q-pa-lg self-start">
    <q-list>
      <q-item-label
        header
      >
        מסלולים
      </q-item-label>

      <q-item
        v-for="route in routes"
        :key="route.title"
        clickable
        :to="route.to"
      >
        <q-item-section
          avatar
        >
          <q-icon name="route" color="primary" />
        </q-item-section>

        <q-item-section>
          <q-item-label>
            <div class="row justify-between">
            {{ route.title }}
            <PathColor :color1="route.color1" :color2="route.color2"/>
            </div>
          </q-item-label>
          <q-item-label caption v-if="route.caption">
            {{ route.caption }}
          </q-item-label>
        </q-item-section>
      </q-item>

      <q-item-label
        header
      >
        נקודות עניין
      </q-item-label>

      <q-item
        v-for="place in places"
        :key="place.title"
        clickable
        :to="place.to"
      >
        <q-item-section
          avatar
        >
          <q-icon name="place" color="primary" />
        </q-item-section>

        <q-item-section>
          <q-item-label>{{ place.title }}</q-item-label>
          <q-item-label caption v-if="place.caption">
            {{ place.caption }}
          </q-item-label>
        </q-item-section>
      </q-item>
    </q-list>
  </div>
</template>

<script>
import PathColor from './PathColor.vue'

const routes = [
  {
    title: 'שביל ואדיות חיפה',
    caption: 'מטיילת רמת אלון דרך ואדי בן-דור לסביוני דניה',
    to: '',
    color1: 'green',
    color2: 'red',
  },
  {
    title: 'שביל העץ הקסום',
    caption: 'מטיילת רמת אלון לפינת היער מעל מגה בעיר',
    to: '',
    color1: 'yellow',
    color2: '#F2F3F4',
  },
  {
    title: 'שביל התצפית',
    caption: 'מואדי בן-דור למאגר המים מעל הטכניון, לרגלי הרכבלית',
    to: '',
    color1: 'red',
    color2: '#F2F3F4',
  },
]
const places = [
  {
    title: 'פינת היער',
    caption: 'כניסה עליונה ליער, מעל מגה בעיר',
    to: ''
  },
  {
    title: 'טיילת רמת אלון',
    caption: 'כניסה תחתונה ליער, בסוף הטיילת',
    to: ''
  },
  {
    title: 'העץ הקסום',
    caption: 'נקודת מנוחה מוצלת בצילו של אלון גדול במסלול העץ הקסום',
    to: ''
  },
  {
    title: 'האלון הגדול',
    caption: 'נקודת מנוחה מוצלת בצילו של אלון בדרך לתצפית מעל הטכניון',
    to: ''
  },
  {
    title: 'בריכת המים של הטכניון',
    caption: 'נקודת תצפית למפרץ מעל הטכניון, ממש מתחת לקו הרכבלית',
    to: ''
  },
]

export default {
  setup () {
    return {
      places,
      routes,
    }
  },
  components: {
    PathColor
}
}
</script>
