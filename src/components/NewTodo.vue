<template>
    <div class="row">
        <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
            <form action="">
                <label>Todo</label>
                <textarea class="form-control" name="" id="" rows="3" v-model="todo"></textarea>
            </form>
        </div>
        <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
            <form action="">
                <button class="btn btn-success" @click.prevent="createNew">Add Todo</button>
            </form>
        </div>
    </div>    
</template>

<script>
export default {
  data: function() {
    return {
      todo: ""
    };
  },
  methods: {
    createNew() {
      this.$emit("todoAdded", this.todo);
      this.todo = "";
    }
  }
};
</script>

<style>
</style>
