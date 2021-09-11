<template>
  <div class="q-pa-lg self-start">
    <q-list>
      <q-item-label
        header
      >
        נקודות במסלול
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
          <q-icon name="place" color="lime-10" />
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
const places = [
  {
    title: 'פינת היער',
    caption: 'יציאה עליונה לשכונה',
    to: ''
  },
  {
    title: 'טיילת רמת אלון',
    caption: 'יציאה תחתונה לשכונה',
    to: ''
  },
  {
    title: 'ואדי שנאק',
    caption: 'מסלול ירוק',
    to: ''
  },
  {
    title: 'ואדי בן-דור',
    caption: 'מסלול אדום-ירוק',
    to: ''
  },
  {
    title: 'העץ הקסום',
    caption: 'אטרקציה',
    to: ''
  },
]

export default {
  setup () {
    return {
      places,
    }
  }
}
</script>
