<template>
<body>

<div class="wrapper">
    <form action="">
        <h1>Login</h1>
        <div class="input-box">
          
          <input id="username" v-model="username" type="text" placeholder="Username" />

        </div>
        <div class="input-box">
          <input id="password" v-model="password" type="password" placeholder="Password" />
            
        </div>
        <div class="remember-forget">
            <label for=""> <input type="checkbox"> Remember Me</label>
            <a href="#">Forget Password</a>
        </div>
        <button  @click="login"   type="submit" class="btn"> Login  </button>
        <div class="register-link">
            <p> Don't have an account? <a href="#"> Register </a></p>
        </div>

    </form>
</div>
</body>
    
  </template>
  
  <script lang="ts">
  import { defineComponent, ref } from 'vue';
  import { useRouter } from 'vue-router';
  
  export default defineComponent({
    name: 'LoginPage',
    setup() {
      const username = ref('');
      const password = ref('');
      const router = useRouter();
  
      const login = () => {
        
       
        // Handle login logic here
        console.log('Login:', username.value, password.value);
      
        router.push('/profile');
        
        
      };
  
      return {
        username,
        password,
        login
      };
    }
  });
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400..700&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

* {
    font-family: 'poppins', sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: url(background-random.jpg) no-repeat;
    background-position: center;
}

.wrapper {
    width: 420px;
    background: transparent;
    border: 3px solid rgba(255, 255, 255, .38);
    backdrop-filter: blur(20px);
    color: #fff;
    border-radius: 36px;
    padding: 42px;
}

.wrapper h1 {
    font-size: 45px;
    text-align: center;
}

.wrapper .input-box {
    position: relative;
    width: 100%;
    height: 50px;
    background: transparent;
    margin: 30px 0px;
}

.input-box input {
    width: 100%;
    height: 100%;
    background: transparent;
    padding: 20px 45px 20px 20px;
    color: #fff;
    font-size: 18px;
    border: none;
    outline: none;
    border: 2px solid #fff;
    border-radius: 30px;
}

.input-box input::placeholder {
    color: #fff;
}

.input-box i {
    position: absolute;
    right: 20px;
    top: 50%;
    transform: translateY(-50%);
    font-size: 24px;
}

.wrapper .remember-forget {
    display: flex;
    justify-content: space-between;
    font-size: 14.5px;
    margin: -15px 0 15px;
}

.remember-forget label input {
    accent-color: #fff;
    margin-right: 3px;
}

.remember-forget a {
    color: #fff;
    text-decoration: none;
}

.remember-forget a:hover {
    text-decoration: underline;

}

.wrapper .btn {
    width: 90%;
    height: 45px;
    background-color: #fff;
    border: none;
    outline: none;
    border: 40px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    cursor: pointer;
    font-size: 16px;
    color: #444;
    font-weight: 600;
    border-radius: 90px;
    margin-left: 5%;
}

.wrapper .btn:hover {
    background: rgba(255, 255, 255, 0.4);
    color: #fff;
    border-color: #fff;
}

.wrapper .register-link {
    font-size: 14.5px;
    text-align: center;
    margin: 20px 0 15px;
}

.register-link p a {
    color: #fff;
    text-decoration: none;
    font-weight: 600;
}

.register-link p a:hover {
    text-decoration: underline;
}
  </style>