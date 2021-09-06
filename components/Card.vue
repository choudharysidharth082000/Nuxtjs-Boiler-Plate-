<template>
    <div class="containor_card">

        <div class="image_card">
            <img :src="image" alt="image">

        </div>
        <div class="header_card">

            <h3>{{heading}}</h3>

            <p>{{discription}}</p>

        </div>

        <div class="buttons">
            <button class="cart">Add to Cart</button>
            <button class="buy">Buy Now</button>


        </div>

    </div>
</template>
<script>
export default {
    name: "Card",
    props:
    {
        heading: {
            type: String
        },
        discription: {
            type: String
        },
        image:
        {
            type: String
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
    font-family: poppins,sans-serif;
}

.containor_card
{
    width: 300px;
    height: 400px;
    
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}
.image_card
{
    width: 100%;
    height: 180px;
    
    object-fit: contain;
}
.image_card img
{
    width: 100%;
    height: 180px;
    object-fit: contain;

}
.header_card
{
    width:100%;
    height: 140px;
    
}

.header_card h3 
{
    font-size: 20px;
    color: #252376;
    padding-top: 10px;
    padding-bottom: 10px;
    padding-left: 10px;
    

}
.header_card p
{
    padding: 2px;
    font-size: 12px;
    color: #252376;
}

.buttons 
{
    width: 100%;
    height: 80px;
    
}
.cart
{
    width: 100%;
    height: 41px;
    border: 1px solid #252376;
    background-color: white;
    margin-bottom: 10px;
    color: #252376;
    
}
.buy
{
    width: 100%;
    height: 41px;
    color: white ;
    background-color: #252376;
    border: none;

}
</style>