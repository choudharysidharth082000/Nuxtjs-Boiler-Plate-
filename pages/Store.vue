<template>
 <div class="containor_main">
    <Navbar />


    <div class="items_containor">

      <div class="card_containor">
         

         <div class="cards" v-for="item in itemList" :key= "item._id">

           <Card :heading="item.heading" :discription= "item.discription" :image= "item.ImageURL"/>

         </div>
      </div>

    </div>

   

    <!-- <ul>

      <li v-for='items in itemList' :key="items._id">
        {{items.heading}}
      </li>
    </ul>
     -->

     
 </div>
</template>

<script>
import Navbar from '../components/Navbar.vue';
import gql from 'graphql-tag';
export default {

  apollo:{
    itemList: gql`
      query itemList{
     itemList
    {
        _id
        heading
        discription
        ImageURL
    }
}
    `} 
    ,
  
  name: 'Index',
  components : 
  {
    Navbar,
    
  },
  

}
</script>
<style scoped>

*
{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: poppins,sans-serif;
}
.items_containor
{
  width: 100%;
  height: 100vh;

  display: flex;
  justify-content: center;
  align-items: center;
}
.card_containor
{
  width: 90%;
  height: 100vh;
  padding: 40px;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
</style>

