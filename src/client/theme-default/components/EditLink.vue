<template>
  <div class="edit-link">
    <a v-if="url" class="link" :href="url" target="_blank" rel="noopener noreferrer">
      {{ text }} <OutboundLink class="icon" />
    </a>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { useEditLink } from '../composables/editLink'
import OutboundLink from './icons/OutboundLink.vue'

export default defineComponent({
  components: {
    OutboundLink
  },

  setup() {
    const { url, text } = useEditLink()

    return {
      url,
      text
    }
  }
})
</script>

<style scoped>
.edit-link {
  padding-top: 1rem;
  padding-bottom: 1rem;
  overflow: auto;
}

.link {
  display: inline-block;
  font-weight: 500;
  color: var(--c-text-light);
}

.link:hover {
  text-decoration: none;
  color: var(--c-brand);
}

.icon {
  margin-left: 4px;
}
</style>
