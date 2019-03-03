<template>
  <v-container class="centered_flex">
    <form v-on:submit.prevent="regBookInfoAPI">
      <v-text-field label="게임 내 아이디 태그를 입력하세요." value="#" prepend-inner-icon="subdirectory_arrow_right" v-model="query" style="width:400px" autofocus></v-text-field>
    </form>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      query: "#"
    };
  },
  methods: {
    regBookInfoAPI: function() {
      const API_URL =
        "https://test-library.cmsedu.co.kr/api/v1/bookData.php?isbn=" +
        encodeURI(this.query);
      //console.log(this.query);
      this.$http
        .get(API_URL)
        .then(res => {
          //console.log(res);
          this.books = res.data.BookData[0];
        })
        .catch(function(err) {
          console.log(err);
        });

      //입력 정보 삭제
      this.query = "";
      //스텝 2로 이동
      this.e1 = 2;
    }
  }
};
</script>

<style>
/* vuetify reset */


/* component */
.centered_flex {display:flex; justify-content: center; align-items: center; height:450px;}
.ico_label {font-size:20px; line-height: 30px;}
</style>
