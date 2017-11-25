<template>
  <div class="row" id="translationForm">
    <div class="col-md-6 col-md-offset-3">
      <form id="transForm" class="well form-inline" v-on:submit="translate">
        <input class="form-control" v-model="translationtext" placeholder="请输入需要翻译的内容">
        <select class="form-control" v-model="language">
          <option value="en">英语</option>
          <option value="ge">德语</option>
          <option value="ko">韩语</option>
          <option value="fr">法语</option>
        </select>
        <input class="btn btn-primary" type="submit" value="翻译">
      </form>
    </div>
  </div>
</template>

<script>

export default {
  name: 'translationForm',
  data() {
    return {
      translationtext: '',
      language: ''
    }
  },
  methods: {
    translate(e) {
      //alert(this.translationtext)
      this.$emit('translate', this.translationtext, this.language)
      e.preventDefault()
    }
  },
  created() {
    this.language = 'en'
  }
}
</script>

<style>
  #transForm {
    border: 1px #ccc solid;
    border-radius: 5px;
  }
</style>
