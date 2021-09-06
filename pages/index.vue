<template>
    <div class="containor">

<!-- left side in the login containor  -->
        <div id="containor_left" class="containor_left">

            <div class="loginbtnright">
                <button @click="clicked" class="login_right">Login Admin</button>

            </div>

            <div class="left_header">

                 <h1>
                Best Place To find your dream <span class="collection">Collection!!!</span>
                </h1>

                <button class="shopbtn"><Nuxt-link to="/store">Shop Now!!</Nuxt-link></button>

            </div>


            
<!-- right side in the login website  -->
           
        </div>
        <div id="containor_right" class="containor_right">

            <div id="right_back" class="right_back">
                <button @click="backClicked">Back</button>
            </div>

            <div class="right_main">

                <div class="right_main_header">
                    <h1>Shopify.io</h1>
                </div>

                <div class="right_main_form">

                    <form id="forms" action="submit">
                        <input id="input1" type="email" placeholder="abc@gmail.com">
                        <input id="input2" type="password" placeholder="password">
                        <button @click="Loginbtn($event)" type="submit" class="loginbtn">Login!!!</button>
                    </form>
                </div>

            </div>

        </div>
    </div>
</template>

<script>
import gql from 'graphql-tag'
export default {
    data()
    {
        return {
        
            // email: document.getElementById('input1').value,
            // password:document.getElementById('input2').value

            email: String,
            password: String
        }

    },
    apollo:
    {
        login:
        {
            query: gql `
                query login ($email: String!, $password: String!) {
    login (email: $email, password: $password) {
        status
        message
        admin {
            firstName
            lastName
            mobileNumber
            email
            title
            password
            isAcive
        }
        accessToken
    }
}
            `,

            variables()
            {
               return {
                   email : this.email,
                   password: this.password
               }
            }
        }

    },

    
   
 
    name : "Login",
    methods: 
    {
        clicked()
        {
            console.log("The function is clicked");
            const rightSection = document.getElementById('containor_right');
            const leftsection = document.getElementById('containor_left');
            const backbtn = document.getElementById('right_back');

            rightSection.style.width = '100%';
            rightSection.style.display = 'block';
            backbtn.style.display = 'block'
            leftsection.style.display = 'none'

            
        },

        backClicked()
        {
            console.log("Button is clicked");
            
            
        },

        Loginbtn(e)
        {
            e.preventDefault();

            const emailForm = document.getElementById('input1').value;
            const passwordForm = document.getElementById('input2').value;
            

            this.email = emailForm;
            this.password= passwordForm

            // if(login.status == true)
            // {
            //     console.log("Successfully Logged in");
            // }
            // else 
            // {
            //     console.log('HE is not logged in');
            // }

            console.log();

            
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
    font-family: 'Poppins', sans-serif;
    
}
a
{
    text-decoration: none;
    color: #252376;
    transition: 0.6s ease in;
}
a:hover 
{
    color: white;
}
.containor
{
    width: 100%;
    height: 100vh;
    background-color:white;
    display: flex;
    
    flex-direction: row;
}
.right_back 
{
    width: 100%;
    height: 60px;
    
    justify-content: flex-end;
    display: none;
}
.right_back button{
    margin: 10px;
    height: 50px;
    width: 132px;
    border: none;
    background-color: white;
    border: 1px solid #252376;
    color: #252376;
    
}
.containor_left
{
    width: 60%;
    height: 100vh;
    background-color: #252376;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.left_header
{
    width: 80%;
    height: 100%;
    
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;

}
.left_header h1
{
    color: white;
    font-weight: 700;
    font-size: 70px;
}
.collection
{
    color: #D6C321;
}
.loginbtnright
{
    width: 100%;
    height: 80px;
    display: flex;
    justify-content: flex-end;
    display: none;
    
}

.login_right
{
    margin: 10px;
    height: 50px;
    width: 132px;
    border: none;
    background-color: #252376;
    border: 1px solid white;
    color: white;
    
}
.shopbtn
{
    margin-left: -50px;
    /* padding: 20px 35px 20px 35px; */
    height: 100px;
    width: 311px;
    background-color: white;
    margin-top: 30px;
    border: none;
    font-family: poppins,sans-serif;
    font-weight: 700;
    font-size: 30px;
    border-radius: 10px;
    color: #252376;
    
    transition: 0.6s ease;
    /* animation: 3s sidharth infinite; */

}
/* @keyframes sidharth {
    0%
    {
        color: #252376;
        background-color: white;
    }
    50%
    {
        color: white;
        background-color: #252376;
        border: 1px solid white;
    }
    1000%
    {
        color: #252376;
        background-color: white;
    }
    
} */
.shopbtn:hover
{
    color: white;
    background-color:#252376;
    border: 1px solid white;

}


.containor_right
{
    width: 50%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items:center;
    flex-direction: column;

}

.right_main
{
    width: 90%;
    height: 90vh;
    
    display: flex;
    flex-direction: column;

}
.right_main_header
{
    width: 100%;
    height: 30%;
    

    display: flex;
    
    justify-content: center;
    align-items: center;
    
    

}

.right_main_header h1
{
    font-weight: 700;
    color: #252376;
    font-size: 65px;
    border: none;
    
    
}

.right_main_form
{
    width: 100%;
    height: 80%;
    
    display: flex;
    justify-content: center;
    /* background-color: black; */
    align-items: center;
    flex-direction: column;
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

#input1, #input2
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

.loginbtn
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
    margin-top: 40px;
    transition: 0.6s ease;
}

.loginbtn:hover
{
    color: #252376;
    background-color: white;
    border: 1px solid #252376;
}

@media screen and (max-width: 1035px) {
     .loginbtnright
  {
      width: 100%;
      
      display: block;
     
  }
  h1
  {
      font-size: 55px;
      
  }

  .containor_left
  {
      width: 100%;
      
  }
  .containor_right
  {
      
      display: none;
  }
}



</style>