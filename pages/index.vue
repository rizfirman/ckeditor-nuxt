<template>
  <client-only>
    <div>
      <div style="display: flex; justify-content: center">
        <VCKEditorVue v-model="text" />
      </div>

      <div v-html="text"></div>
    </div>
  </client-only>
</template>

<script>
let VCKEditorVue
if (process.client) {
  VCKEditorVue = () => import('~/components/editor/VCKEditor.vue')
} else {
  // show nothing on server side

  VCKEditorVue = () => ({
    render: (h) => h('div'),
  })
}

export default {
  data() {
    return {
      text: 'Hello World!!',
    }
  },
  components: {
    VCKEditorVue,
  },
}
</script>
