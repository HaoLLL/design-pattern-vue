<template>
  <div>
      <table>
          <tr>
              <td>编号</td>
              <td>图书名称</td>
              <td>作者</td>
          </tr>
          <tr v-for="item in books">
              <td>{{item.id}}</td>
              <td>{{item.name}}</td>
              <td>{{item.author}}</td>
          </tr>
      </table>

  </div>

</template>
<script>
export default {
    name:"Book",
    data(){
        return {
            books:[{
                id:1,
                name:'java',
                author:'lei'
            }]

        }
    },
    created(){
        axios.get("http://localhost:8181/book/findAll").then((resp)=>{
            console.log("sdfg"+resp);
            this.books = resp.data;
        })
    }
};
</script>
<style scoped>
</style>