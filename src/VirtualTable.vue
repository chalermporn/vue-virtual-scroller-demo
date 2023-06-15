<template>
  <div>
    <virtual-scroller
      :items="items"
      item-height="20"
      content-tag="table"
      page-mode
    >
      <template slot-scope="props">
        <thead v-if="props.itemIndex === 0">
          <tr class="red">
            <th style="position: sticky">Age</th>
            <th style="position: sticky">Name</th>
            <th style="position: sticky">Company</th>
          </tr>
        </thead>
        <tbody>
          <tr :key="props.itemKey">
            <td>{{ props.itemIndex }}</td>
            <td>{{ props.item.name }}</td>
            <td>{{ props.item.company }}</td>
          </tr>
        </tbody>
      </template>
    </virtual-scroller>
  </div>
</template>

<script>
import items from "./data.json";

export default {
  data: () => ({
    items,
  }),
};
</script>