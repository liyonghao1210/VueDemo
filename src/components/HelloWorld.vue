<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <hr />
    <table style="border-collapse: collapse;">
      <thead>
        <tr style="border: 1px solid #ccc;">
          <th style="border: 1px solid #ccc;padding: 5px;">id</th>
          <th style="border: 1px solid #ccc;padding: 5px;">name</th>
          <th style="border: 1px solid #ccc;padding: 5px;">price</th>
        </tr>
      </thead>
      <tbody>
        <tr style="border: 1px solid #ccc;" v-for="(item,index) in books">
          <td style="border: 1px solid #ccc;padding: 5px;">{{item.id}}</td>
          <td style="border: 1px solid #ccc;padding: 5px;">{{item.name}}</td>
          <td style="border: 1px solid #ccc;padding: 5px;">{{item.price}}</td>
        </tr>
        <tr>
          <td colspan="2" style="border: 1px solid #ccc;padding: 5px;">总价格</td>
          <td style="border: 1px solid #ccc;padding: 5px;">{{totalPrice}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App",
      books: [
        { id: 110, name: "javaScript", price: 110 },
        { id: 120, name: "Jquery", price: 12 },
        { id: 130, name: "Vue", price: 34 },
        { id: 130, name: "Vue", price: 34 },
        { id: 130, name: "Vue", price: 34 },
        { id: 140, name: "HTMl", price: 53 }
      ]
    };
  },
  computed: {
    totalPrice: function() {
      let result = 0;
      for (let i = 0; i < this.books.length; i++) {
        result += this.books[i].price;
      }
      return result;
    }
  },
  methods: {}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
