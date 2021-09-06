<template>

<div class="containor_nav">

    <div class="nav_logo">
        <h1>Shopify.io</h1>
    </div>

    <div class="search_form">
        <form action="submit">
            <input id="input" type="text" placeholder="Search">
        </form>
    </div>

    <div class="button_containor">
        <button>Buy Now!</button>
    </div>

</div>
    
</template>
<script>
export default {
    
    name: "Navbar"
}
</script>
<style scoped>
*
{
    margin: 0%;
    padding: 0%;
    font-family: poppins,sans-serif;
    box-sizing: border-box;
}
.containor_nav
{
    height: 100px;
    width: 100%;
    background-color: #252376;
    display: flex;
    justify-content: space-around;
    align-items: center;
    flex-direction: row;
}
.nav_logo

{
    width: 200px;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    
   
}
.nav_logo h1
{
     font-weight: 700;
    font-size: 30px;
    color: white;

}
.search_form
{
    height: 100%;
    width: 493px;
    display: flex;
    justify-content: center;
    align-items: center;
    
}

#input 
{
    background-color: #252375;
    border: none ;
    height: 39px;
    width: 493px;
    border-radius: 20px;
    margin: 10px;
    border: 0.5px solid rgba(255, 255, 255, 0.192);
    
    outline: none;
}
input[type= "text"]
{
    padding-left: 30px;
    font-weight: 600;
    margin-left: 40px;
    font-size: 15px;
    color: rgba(255, 255, 255, 0.651);
}
::placeholder {
  color: rgba(255, 255, 255, 0.63);
  padding: 20px;
  font-size: 15px;
  
  
}
.button_containor
{
    height: 100%;
    width: 200px;
    
    display: flex;
    justify-content: center;
    align-items: center;
}
.button_containor button
{
    width: 130px;
    height: 40px;
    border: none;
    font-weight: 600;
    color: white;
    border: 1px solid white;
    background-color: #252375;
    border-radius: 29.5px;
    transition: 0.2s ease-in;

}
.button_containor button:hover
{
    color: #252375;
    background-color: white;
}

</style>