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
          <q-item-label>{{ route.title }}</q-item-label>
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
const routes = [
  {
    title: 'שביל ואדיות חיפה (ירוק-אדום)',
    caption: 'מטיילת רמת אלון דרך ואדי בן-דור לסביוני דניה',
    to: ''
  },
  {
    title: 'שביל העץ הקסום (צהוב-לבן)',
    caption: 'מטיילת רמת אלון לפינת היער מעל מגה בעיר',
    to: ''
  },
  {
    title: 'שביל התצפית (אדום-לבן)',
    caption: 'מהעץ הקסום לבריכת המים מעל הטכניון',
    to: ''
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
  }
}
</script>
