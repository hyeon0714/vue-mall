<template>
  <div>
    <h1>
      상품등록
    </h1>
    <div>
      <form v-on:submit.prevent="upload" action="">
        <label for="">상품명</label>
        <input type="text"><br>
        <label for="">가격</label>
        <input type="text"><br>
        <label for="">카테고리</label><br>
        <label for="cate">침대</label>
        <input type="radio" name="cate" value="침대">
        <label for="">쇼파</label>
        <input type="radio" name="cate" value="쇼파">
        <label for="">책상</label>
        <input type="radio" name="cate" value="책상"><br>
        <label for="">색상</label><br>
        <label for="color">흰색</label>
        <input type="checkbox" name="color" value="white">
        <label for="black">검은색</label>
        <input type="checkbox" name="color" value="black">
        <label for="wood">우드</label>
        <input type="checkbox" name="color" value="wood"><br>
        <button type="submit">등록</button>
      </form>
    </div>
  </div>
</template>

<script>


export default {
  name: 'ManagerUpload',
  components: {},
  data() {
    return {

    }
  },
  methods: {
    upload(){
      
    }
  }
}
</script>
