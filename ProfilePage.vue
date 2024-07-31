<template>

<div class="dashboard">
        <!-- Sidebar -->
        <div class="sidebar">
            <h2>E-Commerce</h2>
            <ul>
                
                <li><a href="#">Reports</a></li>
                <li><a  @click='logout' href="#">Logout</a></li>
            </ul>
        </div>

        <!-- Main Content -->
        <div class="main-content">
            <!-- Top Navigation Bar -->
            <div class="top-nav">
                <h1>Welcome {{ username }}</h1>
                <p>{{ email }}</p>
                <input type="text" placeholder="Search...">
                <div class="user-info">
                    <span> {{ username }}</span>
                </div>
            </div>

            <!-- Dashboard Widgets -->
            <div class="widgets">
                <div class="widget">
                    <h3>Users</h3>
                    <p>There were 24.936 users in website recently. </p>
                </div>
                <div class="widget">
                    <h3>Views</h3>
                    <p>This web site viewed by 9.861 users in last month.</p>
                </div>
                <div class="widget">
                    <h3>Conversion</h3>
                    <p>7.456</p>
                </div>
                <div class="widget">
                    <h3>Revenue</h3>
                    <p> 5.399 $ (average)</p>
                </div>
            </div>
        </div>
    </div>

  -----------------------------------------------------------------------


    <!-- <div class="profile">
      <h1>User Profile</h1>
      <p><strong>Username:</strong> {{ username }}</p>
      <p><strong>Email:</strong> {{ email }}</p>
      <button @click="logout">Logout</button>
    </div> -->
  </template>
  
  <script lang="ts">
  import { defineComponent, ref,onMounted} from 'vue';
  import { useRoute, useRouter } from 'vue-router';
  
  export default defineComponent({
    name: 'ProfilePage',
    setup() {
      const route = useRoute();
      const router = useRouter();
      const username = ref();
    //const username = ref(); // Replace with dynamic data
      const email = ref(username.value + "@gmail.com"); // Replace with dynamic data
      
      const logout = () => {
        console.log('Logout')
        router.push('/')
      }

      return {
        username,
        email,
        logout
      };
    }
  });
  </script>
  
  <style scoped>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Arial, sans-serif;
}

body,
html {
    height: 100%;

}

.dashboard {
    display: flex;
    height: 100vh;
    background-image: url(background-random.jpg);

}

/* Sidebar styles */
.sidebar {
    backdrop-filter: blur(4px);
    color: #fff;
    width: 250px;
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: start;
    border: 2px solid #fff;
    border-radius: 8px;
}

.sidebar h2 {
    margin-bottom: 20px;
}

.sidebar ul {
    list-style: none;
    width: 100%;
}

.sidebar ul li {
    margin-bottom: 15px;
}

.sidebar ul li a {
    text-decoration: none;
    color: #fff;
    font-size: 18px;
    display: block;
    padding: 10px 15px;
    border-radius: 5px;
    transition: background 0.3s;
}

.sidebar ul li a:hover {
    background-color: #fff;
    color: black;
}

/* Main content styles */
.main-content {
    flex: 1;
    border: 2px solid #fff;
    padding: 20px;
}

/* Top navigation bar styles */
.top-nav {
    color: #fff;
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}

.top-nav h1 {
    font-size: 24px;
}

.top-nav input[type="text"] {
    padding: 10px;
    border-radius: 5px;
    border: 1px solid #ccc;
    width: 250px;
}

.top-nav .user-info {
    display: flex;
    align-items: center;
}

.top-nav .user-info img {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    margin-right: 10px;
}

/* Dashboard widgets styles */
.widgets {
    display: flex;
    flex-wrap: wrap;
    gap: 40px;
    color: #fff;
}

.widget {
    backdrop-filter: blur(14px);
    border: 1px solid #ddd;
    border-radius: 10px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    flex: 1;
    min-width: 200px;
    max-width: 450px;
    padding: 20px;
}

.widget h3 {
    margin-bottom: 10px;
}

.widget p {
    font-size: 18px;
}
  </style>