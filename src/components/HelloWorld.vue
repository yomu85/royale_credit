<template>
  <v-container class="centered_flex">
    <form v-on:submit.prevent="reqUserDataAPI">
      <v-text-field
        label="게임 내 아이디 태그를 입력하세요."
        value="#"
        prepend-inner-icon="subdirectory_arrow_right"
        v-model="query"
        style="width:400px"
        autofocus
      ></v-text-field>
    </form>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      query: "#2LUYRPV8"
    };
  },
  methods: {
    reqUserDataAPI: function() {
      const API_URL =
        //"https://api.clashroyale.com/v1/players/" + encodeURI(this.query);
        "https://api.clashroyale.com/v1/players/%232LUYRPV8";
      //console.log(this.query);
      const AuthStr =
        "Bearer " +
        "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiIsImtpZCI6IjI4YTMxOGY3LTAwMDAtYTFlYi03ZmExLTJjNzQzM2M2Y2NhNSJ9.eyJpc3MiOiJzdXBlcmNlbGwiLCJhdWQiOiJzdXBlcmNlbGw6Z2FtZWFwaSIsImp0aSI6IjZjYWY5MjYxLWMwMWUtNDkzOC05ODlhLTI2MDFjYmMwMTEwNiIsImlhdCI6MTU1MTY4NjQ4MSwic3ViIjoiZGV2ZWxvcGVyLzdmNjJkMTA5LWMyY2QtYjI3NS04MDhiLTFjYWZjNGVhNjU5NiIsInNjb3BlcyI6WyJyb3lhbGUiXSwibGltaXRzIjpbeyJ0aWVyIjoiZGV2ZWxvcGVyL3NpbHZlciIsInR5cGUiOiJ0aHJvdHRsaW5nIn0seyJjaWRycyI6WyIxMTIuMjE2LjM4LjIiXSwidHlwZSI6ImNsaWVudCJ9XX0.fu5xokRN3XW44t0494iZq9XOQd0SBYsSR9IjxYsoN_IpdWWopw2aGa1evd_AwVrx2x1Toi8w8y56ELPBkAI1uw";
      this.$http
        .get(API_URL, {
          headers: {
            Authorization: AuthStr
          }
        })
        .then(res => {
          console.log(res);
          //this.books = res.data.BookData[0];
        })
        .catch(function(err) {
          console.log(err);
        });
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
