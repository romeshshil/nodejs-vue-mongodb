<template>
  <div>

<div class="card" style="margin-top:50px">
  <div class="card-header">
    <h3>Create Item</h3>
  </div>
  <div class="card-block">
  <div class="container" style="padding:20px">
     <form v-on:submit.prevent="addItem">
      <div class="row">
        <div class="col-md-6">
          <div class="form-group">
            <label>Item Name:</label>
            <input type="text" class="form-control" v-model="item.name">
          </div>
        </div>
        </div>
        <div class="row">
          <div class="col-md-6">
            <div class="form-group">
              <label>Item Model:</label>
              <input type="text" class="form-control" v-model="item.model" />
            </div>
          </div>
        </div>

         <div class="row">
          <div class="col-md-6">
            <div class="form-group">
              <label>Item Price:</label>
              <input type="text" class="form-control" v-model="item.price" />
            </div>
          </div>
        </div><br />

        <div class="form-group">
          <button class="btn btn-primary">Add Item</button>
        </div>
    </form>
    </div>
  </div>
</div>

  </div>
</template>
<script>
  export default {
    data(){
        return{
          item:{}
        }
    },
    methods: {
      addItem(){
        let uri = 'http://localhost:4000/items/add';
        this.axios.post(uri, this.item).then((response) => {
          this.$router.push({name: 'DisplayItem'})
        })
    }
  }
}
</script>
