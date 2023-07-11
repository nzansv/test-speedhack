<template>
  <div class="sidebar">
    
  <div class="side-header">
    <img alt="site logo" class="logo" src="@/assets/logo.svg" />  
  </div>
  <div class="side-menu">
    <ul class="side-menu-links">
      <li>
        <a href="">
          <img class="icon home" src="@/assets/icon/home.svg" />  
          <span class="link-name">Кабинет</span>
          <span class="notify-num">12</span>
        </a>
      </li>
      <li>
        <a href="">
          <img class="icon courses" src="@/assets/icon/courses.svg" />  
          <span class="link-name">Курсы</span>
        </a>
      </li>
      <li>
        <a href="">
          <img class="icon tasks" src="@/assets/icon/tasks.svg" />  
          <span class="link-name">Задания</span>
          <span class="notify-num">7</span>
        </a>
      </li>
      <li>
        <a href="">
          <img class="icon stats" src="@/assets/icon/stats.svg" />  
          <span class="link-name">Статистика</span>
          <span class="notify-num">5</span>

        </a>
      </li>
      <li>
        <a href="">
          <img class="icon settings" src="@/assets/icon/settings.svg" />  
          <span class="link-name">Настройки</span>
        </a>
      </li>
    </ul>
  </div>
  </div>
</template>

<style scoped>
.sidebar { 
  background-color: #F5F7F9;
  padding: 3rem 2rem;
  width: 280px;
  height: 100%;
  position: fixed;
  top: 0;
  font-family: "Gilroy-Medium";
  left: 0;
  bottom: 0;
 }
  .side-menu {
    height: 100%;
    width: 100%;
    margin-top: 40px;
    height: calc(100%-90px);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-content: end;
  }  
  .side-menu li {
    list-style: none;
    padding: 0 10px;
  }
  .icon {
    width: 44px;
    padding: 0 10px;
    display: flex;
    align-items: center;
    height: 100%;
    /* Other styles here */
}
  .side-menu li a{
    font-size: 16px;
    text-decoration: none;
    height: 58px;
    display: flex;
    align-items: center;
    justify-content: start;
    position: relative;
    color: black;
  }
  .notify-num{
    color: white;
    background-color: #F94874;
    width: 24px;
    height: 24px;
    border-radius: 100%;
    text-align: center;
    line-height: 24px;
    font-size: 12px;
    justify-self: end;
    position: absolute;
    right: 0;
  }
  
  .side-header{
    justify-content: center;
    display: flex;
    align-items: center;
  }


  .side-menu-links li a:hover .icon, 
  .side-menu-links li a:hover .link-name, .side-menu-links li:hover{
    color: white;
    fill: white;
    background-color: black;
    border-radius: 11px;
  }

  .side-menu-links li a:hover .home{
    content: url("@/assets/icon/light-home.svg");
  } 
  .side-menu-links li a:hover .courses{
    content: url("@/assets/icon/courses-light.svg");
  }
  .side-menu-links li a:hover .tasks{
    content: url("@/assets/icon/tasks-light.svg");
  }
  .side-menu-links li a:hover .stats{
    content: url("@/assets/icon/stats-light).svg");
  }
  .side-menu-links li a:hover .settings{
    content: url("@/assets/icon/settings-light.svg");
  }
</style>
