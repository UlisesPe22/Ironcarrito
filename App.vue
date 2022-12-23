<template>
<div>
  <h1>IronCart</h1>
<table>
    <tbody>
        <tr >
          <td v-for="(item,index) in datos ">
            {{ item.name }}  <h4>Subtotal: {{ datos[index].quantity *datos[index].price }}$</h4>
          </td>
        </tr>
         <tr >
          <td v-for="(item,index) in datos">
           {{ item.price }} <button @click="add(index)">+</button> <button @click="less(index)">-</button> 
          </td>
        </tr>
        </tbody>
</table>
<div>
  <tr v-for="(item,index) in datos ">
            {{ item.name }}  Quantity:{{ datos[index].quantity }}
  </tr>
</div>
<div>
  <h2>Total: {{ total }}$</h2>
</div>
</div>

</template>
<script>
export default {
  data() {
    return{
      datos: [
    {
      "uuid": "3",
      "name": "Vectorify",
      "description": "User Experience Design",
      "content": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
      "image": "https://github.com/ironhack-jc/mid-term-api/blob/main/3.jpg?raw=true",
      "purshased_at": "June 10, 2021",
      "price": 5.5,
      "quantity": 0,
      "active": true
    },
    {
      "uuid": "2",
      "name": "Dashcoin",
      "description": "Web Development",
      "content": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
      "image": "https://github.com/ironhack-jc/mid-term-api/blob/main/2.jpg?raw=true",
      "purshased_at": "June 10, 2021",
      "price": 4.5,
      "quantity": 0,
      "active": true
    },
    {
      "uuid": "6",
      "name": "Lorem ipsum",
      "description": "Lorem ipsum",
      "content": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
      "image": "https://github.com/ironhack-jc/mid-term-api/blob/main/6.jpg?raw=true",
      "purshased_at": "June 10, 2021",
      "price": 10.5,
      "quantity": 0,
      "active": false
    },
    {
      "uuid": "4",
      "name": "Lorem ipsum four",
      "description": "Lorem ipsum",
      "content": "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
      "image": "https://github.com/ironhack-jc/mid-term-api/blob/main/4.jpg?raw=true",
      "purshased_at": "June 10, 2021",
      "price": 100.5,
      "quantity": 0,
      "active": true
    },
    {
      "uuid": "1",
      "name": "Simplify",
      "description": "UI Design & App Development",
      "content": "Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et! Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi. Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt quix duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.<br><br>Aliqua id fugiat nostrud irure ex duis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad e dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisis ea quis id quis ad et. Sunt qui esse pariatur duis deserunt mollit dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nisi.Aliqua id fugiat nostrud irure ex duis ea quis id quis ad e dolore cillum minim tempor enim. Elit aute irure tempor cupidatat incididunt sint deserunt ut voluptate aute id deserunt nis cillum minim tempor enim.",
      "image": "https://github.com/ironhack-jc/mid-term-api/blob/main/1.jpg?raw=true",
      "purshased_at": "June 22, 2021",
      "price": 4,
      "quantity": 0,
      "active": true
    }
  ],
     total : 0,
    }
   
  },
  methods:{
    add(index){
      this.total= this.total + this.datos[index].price
      this.datos[index].quantity +=1
    },
    less(index){
      this.total= this.total - this.datos[index].price
      this.datos[index].quantity -=1 
    },
  
  }
}
</script>