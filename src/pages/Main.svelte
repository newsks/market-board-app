<script>
    let hour=new Date().getHours()
    let min=new Date().getMinutes()
</script>

<div class="media-info-msg">화면사이즈를 줄여주세요</div>
    <!-- 헤더바 -->
    <header>
      <!-- 인포바 -->
      <div class="info-bar">
        <div class="info-bar__time">{hour}:{min}</div>
        <div class="info-bar__icons">
          <img src="assets/chart-bar.svg" alt="chart-bar" />
          <img src="assets/wifi.svg" alt="wifi" />
          <img src="assets/batter.svg" alt="battery" />
        </div>
      </div>
      <!-- 메뉴바 -->
      <div class="menu-bar">
        <div class="menu-bar__location">
          <div>역삼1동</div>
          <div class="menu-bar__location--icon">
            <img src="assets/arrow.svg" alt="arrow" />
          </div>
        </div>
        <div class="menu-bar__icons">
          <img src="assets/search.svg" alt="search" />
          <img src="assets/menu.svg" alt="menu" />
          <img src="assets/bell.svg" alt="alert" />
        </div>
      </div>
    </header>
    <!-- 메인 -->
    <a class="btn-write" href="#/write">+ 글쓰기</a>
    <main>
     
    </main>
    <!-- footer -->
    <footer>
      <div class="footer-block">
        <div class="footer-icons">
          <div class="footer-icons__img">
            <img src="assets/home.svg" alt="home" />
          </div>
          <div class="footer-icons__desc">홈</div>
        </div>
        <div class="footer-icons">
          <div class="footer-icons__img">
            <img src="assets/paper.svg" alt="paper" />
          </div>
          <div class="footer-icons__desc">동네생활</div>
        </div>
        <div class="footer-icons">
          <div class="footer-icons__img">
            <img src="assets/map.svg" alt="map" />
          </div>
          <div class="footer-icons__desc">내 근처</div>
        </div>
        <div class="footer-icons">
          <div class="footer-icons__img">
            <img src="assets/chat.svg" alt="chat" />
          </div>
          <div class="footer-icons__desc">채팅</div>
        </div>
        <div class="footer-icons">
          <div class="footer-icons__img">
            <img src="assets/user.svg" alt="user" />
          </div>
          <div class="footer-icons__desc">나의 당근</div>
        </div>
      </div>
    </footer>