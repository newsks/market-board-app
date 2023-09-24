<script>
  import { getAuth, signInWithPopup, GoogleAuthProvider } from "firebase/auth";
  import { user$ } from "../store";

  const provider = new GoogleAuthProvider();
  const auth = getAuth();

  const loginWithGoogle = async ()=>{
    try{
      const result= await signInWithPopup(auth, provider)
      const credential = GoogleAuthProvider.credentialFromResult(result);
      const token = credential.accessToken;
      const user = result.user;
      user$.set(user)
      localStorage.setItem('token', token)
    }catch(error){
      console.error(error)
    }
  }
  
</script>

<div class="login_bg">
  <div class="login_area">
    <h1>로 그 인 하 기</h1>
   <button class="login-btn" on:click={loginWithGoogle}>
      <div class="g_logo"> <img src="assets/goole_logo.jpg" alt="logo" />로 시작하기</div>
  </button>
</div>
</div>

<style>
  .login_bg{
    width: 100vw;
    height: 100vh;
    background-color: rgb(211, 253, 253);
    display: flex;
    justify-content: center;
    align-items: center;
    background: #f7f7f7;
  }
  .login_area h1 {
    font-size: 16px;
    padding-bottom: 10px;
    color: #414449;
  }
  .login_area{
    width: 500px;
    height: 30%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .g_logo{
    width: 220px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .g_logo img {
    width: 80px;
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