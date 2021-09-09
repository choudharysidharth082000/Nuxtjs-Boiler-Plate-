<template>
 <div class="containor_main">
    <Navbar />

    <div class="containor_options">

      
        <div class="button3">

            <button class=" btn-success add"><nuxt-link to="/adminpanel/createItems">Add Item</nuxt-link></button>

        </div>

    </div>


    <div class="items_containor">

      <div class="card_containor">
         

         <div class="cards" v-for="item in itemList" :key= "item._id">

           <CardAdmin class="original" :heading="item.heading" :discription= "item.discription" :image= "item.ImageURL" :id= "item._id"/>

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
import Navbar from '../../components/Navbar.vue';
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
a
{
    text-decoration: none;
    color: white;
}
.items_containor
{
  width: 100%;
  height: 100%;

  display: flex;
  justify-content: center;
  align-items: center;
}
.card_containor
{
  width: 90%;
  height: 100%;
  padding: 40px;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
.cards
{
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
.original 
{
  margin: 30px;
}

.containor_options 
{
    width: 100%;
    height: 100px;
    
}
.button3
{
  
    display: flex;
    justify-content: center;
    align-items: center;
}
.add
{
    border: none;
    width: 100%;
    height: 40px;

}


@media screen and (max-width: 927px) {


  .search_form
  {
    display: none;
  }
}
</style>

