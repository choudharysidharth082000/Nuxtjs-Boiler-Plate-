<template>
<div class="containor_items">

    <div class="middle_items">

        <div class="mddle_main_items">

            <div class="middle_main_heading">
                <h1>Shopify.io</h1>
            </div>

            <div class="middle_main_form">
                <form action="" @submit.prevent="createItem($event)">
                    <input v-model="heading" id="input1" type="text" placeholder="Heading">
                    <input v-model="discription" id="input2" type="text" placeholder="Discription">
                    <input v-model="ImageURL" id="input3" type="text" placeholder="ImageURL">
                     <div class="buttonsubmit">
                <button class="btnSubmit" type="submit">Submit</button>
            </div>

                </form>
            </div>


           
        </div>

    </div>

</div>


    
</template>
<script>
import gql from 'graphql-tag'
export default {
    name: "Items",

    data()
    {
        return {
            heading: '',
            discription : '',
            ImageURL: ''
        }
    },
    methods:
    {
        createItem(event)
        {
            this.$apollo.mutate({
                mutation: gql `
                   mutation($createItemItemValues: iteminput)
{
  createItem(itemValues: $createItemItemValues) {
    item {
      discription
      heading      
      ImageURL
    }
  }
}
                `,
                variables:
                {
                    createItemItemValues :
                    {
                        heading: this.heading,
                        discription: this.discription,
                        ImageURL: this.ImageURL
                    }
                }
            }).then(data=>
            {
                event.target.reset();
                alert('The Item is Successfully added to the Database');
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
    height: 100vh;
    widows: 100%;
    
    display: flex;
    justify-content: center;
    align-items: center;

}
.middle_items
{
    width: 80%;
    height: 100vh;
    
    display: flex;
    justify-content: center;
    align-items: center;
}
.mddle_main_items
{
    width: 60%;
    height: 100vh;
    

}
.middle_main_heading 
{
    width: 100%;
    height: 200px;
    
    display: flex;
    justify-content: center;
    align-items: center;
}

.middle_main_heading h1
{
     font-weight: 700;
    color: #252376;
    font-size: 65px;
    border: none;
}
form
{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}
.middle_main_form
{
    width: 100%;
    
    height: 300px;
    
    
    display: flex;
    justify-content: center;
    align-items: center;
}

input
{
    width: 100%;
}

form
{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

#input1, #input2 , #input3
{
    background-color: #d8d8e41f;
    border: none ;
    height: 62px;
    width: 494px;
    border-radius: 9px;
    margin: 10px;
    border: 0.5px solid rgba(0, 0, 0, 38%);
    
    outline: none;
    
}
input[type= "text"]
{
    padding-left: 30px;
    margin-left: 40px;
    font-size: 20px;
}
::placeholder {
  color: rgba(2, 23, 24, 0.295);
  padding: 20px;
  font-size: 20px;
  
  
}
.buttonsubmit 
{
    width: 100%;
    height: 90px;
    display: flex;
    justify-content: center;
    

    margin-bottom: 20px;
    
}
.btnSubmit 
{
    height: 62px;
    width: 494px;
    background-color: #252376;
    font-family: poppins,sans-serif;
    font-weight: 600;
    color: white;
    font-size: 20px;
    border: none;
    outline: none;
    
    transition: 0.6s ease;
}
@media screen and (max-width: 1035px)
{
    .middle_main_heading h1
{
     font-weight: 700;
    
    font-size: 55px;
    border: none;
}
.middle_items
{
    width: 100%;
}

#input1, #input2 , #input3
{
    background-color: #d8d8e41f;
    border: none ;
    height: 52px;
    width: 334px;
    border-radius: 9px;
    margin: 10px;
    border: 0.5px solid rgba(0, 0, 0, 38%);
    
    outline: none;
    
}
input[type= "text"]
{
    padding-left: 30px;
    margin-left: 40px;
    font-size: 20px;
}
::placeholder {
  color: rgba(2, 23, 24, 0.295);
  padding: 20px;
  font-size: 20px;
  
  
}
.middle_main_form
{
    width: 100%;
    
    
    height: 300px;
    
    display: flex;
    justify-content: center;
    align-items: center;
}
.mddle_main_items{
    width: 100%;
}
.buttonsubmit 
{
    align-items: center;
}
.btnSubmit 
{
    width: 334px;
    border-radius: 3px;
}


}

</style>