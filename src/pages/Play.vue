<template>
    <q-page padding>
        <div class="row q-gutter-xl">
      <div class="col">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore, eaque. Nihil odit quod iure debitis quibusdam provident? Dolorum est culpa earum quos sequi, tempora a reiciendis quaerat, voluptatum totam eum.
        <div>
            <q-btn color="teal" @click="showLoading" label="Show Loading"/>
            <q-btn color="primary" label="Primary" @click = "handleClick"/>
            <q-input outlined v-model="myInput" label="Outlined"/>
        </div>
         <p v-for="n in 55" :key="n">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugit nihil praesentium molestias a adipisci, dolore vitae odit, quidem consequatur optio voluptates asperiores pariatur eos numquam rerum delectus commodi perferendis voluptate?
          </p>

          <!-- place QPageScroller at end of page -->
          <q-page-scroller position="bottom-right" :scroll-offset="150" :offset="[18, 18]">
            <q-btn fab icon="keyboard_arrow_up" color="accent" />
          </q-page-scroller>
      </div>
      <div class="col">
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Consectetur, optio accusamus. Temporibus, dolor quas. Aliquid optio aut odit a ut sit, beatae quidem, ullam suscipit eum tenetur, perferendis inventore expedita.
      </div>
    </div>
    </q-page>
</template>

<script>
export default {
  data () {
    return {
      myInput: ''
    }
  },
  methods: {
    handleClick () {
      this.myInput = 'Click'
    },
    showLoading () {
      this.$q.loading.show({
        message: 'Some important process is in progress. Hang on..'
      })

      // hiding in 3s
      this.timer = setTimeout(() => {
        this.$q.loading.hide()
        this.timer = undefined
      }, 3000)
    }
  }
}
</script>
