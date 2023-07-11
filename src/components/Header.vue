<script>
export default {
name: 'Header'
}
</script>
<template>
    <header class="header">
      <div class="greet-block">
        
      <div class="header-wellcome-card">
        <h1><span>Привет, Арман!</span><img src="@/assets/icon/emoji.svg" alt=""></h1>
        <p>Давай научимся чему-то новому! </p>
      </div>
      </div>
      <div class="info-block">
        <div class="header-search">
        <input type="text" placeholder="Поиск">
        <img src="@/assets/icon/uil_search.svg" alt="Image">
      </div>
      <div class="notification dropdown">
        <button class="image-button dropbtn"><img src="@/assets/icon/notify.svg" alt="Image"></button>
        <div class="dropdown-content" >
          <ul class="dropdown-list">
            <li>
              <p class="link-name">Окончание подписки</p>
              <p class="link-description"><span>Напоминаем, что необходимо продлить по...</span>
                <span class="notify-num">
                  <img src="@/assets/icon/goto.svg" alt="Image">
                </span>
              </p>
            </li>
            <li>
              <p class="link-name">Доступны новые курсы</p>
              <p class="link-description"><span>Представляем вашему вниманию обновленный спис...</span>
                <span class="notify-num">
                  <img src="@/assets/icon/goto.svg" alt="Image">
                </span>
              </p>
            </li>
            <li>
              <p class="link-name">Сообщение от учителя</p>
              <p class="link-description"><span>Привет, Арман! Хотел сообщить, что твоя домашка...</span>
                <span class="notify-num">
                  <img src="@/assets/icon/goto.svg" alt="Image">
                </span>
              </p>
            </li>
          </ul>
      </div>
      </div>
      <div class="header-avatar dropdown">
        <img alt="site logo dropbtn" class="logo" src="@/assets/profile.png" />  
        <div class="dropdown-content" >
          <ul class="dropdown-list profile">
            <li class="menu-item">
              <p class="link-name">Юсупов А.</p>
              <p class="link-description"><span>11 класс</span>
              </p>
            </li>
            <li class="menu-item">
              <p class="menu-item">
                <img class="icon" src="@/assets/icon/pen.svg" />  
                <span class="link-name menu-item">Настройка профиля</span></p>
            </li>
            
            <li class="menu-item">
              <p class="menu-item">
                <img class="icon" src="@/assets/icon/aim.svg" />  
                <span class="link-name">Достижения</span></p>
            </li>
            <li class="menu-item">
              <p class="menu-item">
                <img class="icon" src="@/assets/icon/global.svg" />  
                <span class="link-name">Cменить язык</span></p>
            </li>
            <li class="menu-item">
              <p class="menu-item">
                <img class="icon" src="@/assets/icon/logout.svg" />  
                <span class="link-name">Выход</span></p>
            </li>
          </ul>
      </div>
      </div>
      </div>
      
    </header>
  </template>
  <style scoped>
  .dropbtn {
  background-color: #4CAF50;
  color: white;
  padding: 16px;
  font-size: 16px;
  border: none;
  cursor: pointer;
}
.menu-item {
  border-bottom: none!important;
  padding: .2rem 0!important;
}
.dropdown {
  position: relative;
  display: inline-block;
}

.icon{
  margin-right: 10px;
}

.dropdown-list .link-name {
  font-size: 12px;
  font-family: "Gilroy-Bold";
}

.dropdown-list li {
  border-bottom: 1px solid #E7EAE9;
  padding: 1rem 0;
}
.dropdown-list li:last-child {
  border-bottom: none;
  padding-top: 1rem;
  padding-bottom: 0;
}
.dropdown-list li:first-child {
  padding-top: 0;
}
.dropdown-list .link-description {
  font-size: 9px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.notify-num{
    color: white;
    background-color: #F94874;
    min-width: 24px;
    min-height: 24px;
    border-radius: 100%;
    text-align: center;
    line-height: 24px;
    justify-self: end;
    margin-left: 10px;
  }

.dropdown-content {
  border: 1px solid #E7EAE9;
  display: none;
  position: absolute;
  border-radius: 15px;
  min-width: 200px;
  padding: 1rem;
  background-color: white;
  z-index: 10;
  right: 0;
}

.dropdown-content a:hover {background-color: #f1f1f1}

.dropdown:hover .dropdown-content {
  display: block;
}

  .header-wellcome-card h1{
    font-size: 24px;
    font-family: "Gilroy-Bold";
    display: flex;
  }
  .greet-block, .info-block {
    display: flex;
    justify-content: space-between;
    align-content: center;
    align-items: center;
    gap: 30px;
  }
  .header-wellcome-card p{
    color: #85878D;
    font-size: 14px;
  }
  button{
    margin-right: 0;
    margin-top: 0;
  }
  .image-button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      background-color: white;
      border: 1px solid #E7EAE9;
      padding: 10px 10px;
      border-radius: 12px;
      margin: 0;
      cursor: pointer;
    }
    .image-button img {
      height: 24px;
    }
    .header {
      display: flex;
      width: 100%;
      flex-direction: row;
      justify-content: space-between;
    }
    .header-search input{
      font-size: 16px;
      border-radius: 12px;
      font-size: 14.5px;
      border: 1px solid #E7EAE9;
      padding: 0 25px 0 20px;
      color: #85878D;
      height: 100%;
      width: 100%;
    }

    .header-search {
      position: relative;
      height: 45px;
      max-width: 217px;
      margin: 0 30px;
    }

    .header-search img{
      position: absolute;
      font-size: 22px;
      right: 0;
      z-index: 10;
      height: 24p;
      margin-right: 1rem;
      top: 50%;
      transform: translateY(-50%);
    }


  </style>