<template>
  <q-page class="column items-center justify-between">
    <welcome />
    <route-map />
    <locations />
    <q-img src="side_monster_blue.jpg"/>
  </q-page>
</template>

<script lang="ts">
import { Todo, Meta } from 'components/models';
import Locations from 'components/Locations.vue';
import RouteMap from 'components/RouteMap.vue';
import Welcome from 'components/Welcome.vue';
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'PageIndex',
  components: { Locations, RouteMap, Welcome },
  setup() {
    const todos = ref<Todo[]>([
      {
        id: 1,
        content: 'ct1'
      },
      {
        id: 2,
        content: 'ct2'
      },
      {
        id: 3,
        content: 'ct3'
      },
      {
        id: 4,
        content: 'ct4'
      },
      {
        id: 5,
        content: 'ct5'
      }
    ]);
    const meta = ref<Meta>({
      totalCount: 1200
    });
    return { todos, meta };
  }
});
</script>
