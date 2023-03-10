<template>
  <div class="container fuild-set bg-light px-0">
    <div class="col-10 alert alert-success mt-3 mx-auto text-center" role="alert" id="alert">Здесь будут отображаться заказы, которые сотрудник может принять в работу</div>
    <div>{{this.content}}</div>
  </div>
</template>

<script>
  export default {
    name: "tasks",
    data() {
      return {
        content: null
      }
    },
    methods: {
      publicData() {
        // GET DATA

        // We don't need to authenticate if the public role has access to some_public_collection.
        const publicData = await directus.items('https://i0te4rix.directus.app/admin/content/order_process').readByQuery({ status: ['status'] })

        this.content = publicData.data
      }
    },
  }
</script>

<style>

</style>