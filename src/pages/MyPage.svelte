<script>
  import Header from "../components/Header.svelte";
  import Nav from "../components/Nav.svelte";
  import { user$ } from "../store";

  const logout =()=>{
    user$.set(null);
    localStorage.removeItem("token")
  }
</script>

<Header/>
<div class="login_bg">
    <div class="login_area">
      <h1>나의 당근</h1>
     <button class="login-btn" on:click={logout}>
        <div class="g_logo"> 로그아웃</div>
    </button>
  </div>
  </div>
<Nav location='my'/>

<style>
    .login_bg{
      width: 100vw;
      height: 60vh;
      display: flex;
      justify-content: start;
      align-items: center;
    }
    .login_area h1 {
      font-size: 16px;
      padding-bottom: 10px;
      color: #414449;
    }
    .login_area{
      width: 500px;
      display: flex;
      flex-direction: column;
      justify-content: start;
      align-items: center;
    }
    
    .login-btn{
      display: flex;
      justify-content: center;
      align-items: center;
      border: 1px solid #e0e0e0;
      background-color: #fff;
      padding: 20px 30px;
      border-radius: 10px;
      box-shadow: 1px 1px 1px 1px gray;
    }
    .login-btn:hover {
      opacity: 80%;
    }
  </style>