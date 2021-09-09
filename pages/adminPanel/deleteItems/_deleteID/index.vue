<template>
<div class="containor_items">


    <div class="main_items">

        <div class="header_items">
            <h1>Alert!!!</h1>
        </div>

        <div class="middle_content">
            <p>The Item that you have chosen is going to delete!! . Please Select the Following Options Below</p>

            
        </div>

        <div class="buttons_content">

            <button @click="createItem" class="btncontent1">Delete!!!</button>
            <button class="btncontent2">Go Back</button>


        </div>

    </div>

   

</div>


    
</template>
<script>
import gql from 'graphql-tag'
export default {
    name: "Items",

    methods:
    {
        createItem()
        {
            this.$apollo.mutate({
                mutation: gql `
                  mutation($deleteItemIdData: String)

{
  deleteItem(idData: $deleteItemIdData) {
    accessToken
    message
    status
  }
}
                `,
                variables:
                {
                    deleteItemIdData: this.$route.params.deleteID
                    
                }
            }).then(data=>
            {
                
                alert('The Item is deleted Successfully');
                  window.location.replace("/adminPanel");

            })
        }
    }
    
}
</script>

<style scoped>

*
{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: poppins, sans-serif;
}
.containor_items
{
    width: 100%;
    height: 100vh;
    background-color: #efefef;
    display: flex;
    justify-content: center;
    align-items: center;
}
.main_items
{
    width: 60%;
    height: 60%;
    background-color: white;
}
.header_items
{
    width: 100%;
    height: 40%;
    
    display: flex;
    justify-content: center;
    align-items: center;
}
.header_items h1
{
    color: rgb(224, 48, 48);
    font-size: 55px;
}
.middle_content
{
    width: 100%;
    height: 40%;
    
    display: flex;
    justify-content: center;
    align-items: center;
}
.middle_content p
{
    font-size: 20px;
    text-align: center;
    padding: 10px;
}
.buttons_content
{
    widows: 100%;
    height: 20%;
    
    display: flex;
    justify-content: space-around;
    align-items: center;
}
.btncontent1
{
    height: 50px;
    width: 170px;
    background-color:rgb(224, 48, 48) ;
    color: white;
    border: none;
    border-radius: 6px;
    transition: 0.6s ease;

}
.btncontent2
{
    height: 50px;
    width: 170px;
    border: 1px solid rgb(224, 48, 48);
    background-color: white;
    
    color: rgb(224, 48, 48);
    
    border-radius: 6px;
    transition: 0.6s ease;

}
.btncontent1:hover 
{
    color: white;
    background-color: rgb(240, 61, 61);
    

}
@media screen and (max-width : 738px)
{
    .main_items
    {
        width: 80%;
        height: 80%;
    }
    

}
@media screen and (max-width : 380px) {
    
    /* .buttons_content
    {
        flex-direction: column;
    } */
    .main_items
    {
        width: 100%;
        height: 100%;
    }

    .middle_content
    {
        height: 20%;
    }
    
}
</style>