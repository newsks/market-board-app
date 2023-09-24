<script>
     let hour=new Date().getHours()
    let min=new Date().getMinutes()
</script>

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