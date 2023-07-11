<script>
export default {
name: 'Announcement'
}
</script>
<template>
  <div class="wrapper">
    <h1 class="block-title">Объявления</h1>
    <div class="carousel">
      <div class="inner">
        <div class="card">
          <div class="card-stat">
            <div class="stat-img">
              <img src="@/assets/teacher1.png" alt="">
            </div>
            <div class="stat-detail">
              <h1>Не забудьте про тест!!!</h1>
              <p>Алия Молдашевна</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Ребята, на этой неделе мы сдаем пробный тест по Географии, так что готовьтесь хорошенько по последним темам, и не забудьте о том, что...</h1>
          </div>
          <div class="card-info">
            <button  class="btn"><span>Читать полностью →</span></button>
          </div>
        </div>
        
        <div class="card" >
          
          <div class="card-stat"  >
            <div class="stat-img">
              <img src="@/assets/teacher2.png" alt="">
            </div>
            <div class="stat-detail">
              <h1>Про домашнее з...</h1>
              <p>Егор Крид</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Уважаемые ученики! Просьба прикреплять домашние задание в формате Word файла, чтобы я мог корректировать ваши ошибк...</h1>
          </div>
          <div class="card-info">
            <button class="btn"><span>Читать полностью →</span></button>
          </div>
        </div>

      </div>
    </div>
  </div>
    
  </template>
  
  <style scoped>
  .wrapper{
    width: 100%;
  }
  .btn {
    border: none;
    border-radius: 12px;
    font-family: "Gilroy-Bold";
    color: #F94874;
    text-align: start;
    cursor: pointer;
    background-color: transparent;
  }
  .btn img {
    fill: #F94874;
  }
  .btn img {
    margin-left: 11px;
  }
  .block-title{
    font-family: "Gilroy-Bold";
    font-size: 20px;
  }
  .carousel {
    width: 100%;
    display: flex;
    overflow: hidden;
  }
  .stat-img{
    min-width: 50px;
    min-height: 50px;
    border-radius: 100%;
    text-align: center;
    line-height: 50px;
    justify-content: center;
    align-items: center;
    display: flex;
    margin-right: 10px;
  }
  .inner {
    transition: transform 2s;
    white-space: nowrap;
  }
  .stat-detail{
    white-space: wrap;
    line-height: 17px;
  }
  .card-stat{
    display: flex;
    align-items: start;
    flex-direction: row;
  } .card-stat h1 {
      font-family: Gilroy-Bold;
      font-size: 16px;
  } .card-stat p {
    font-size: 10px;
    color: black;
    opacity: 50%;
    }
    .card-title{
      align-self: center;
    }
    .card-title h1{
      font-family: Gilroy-Bold;
      font-size: 9px;
      text-align: start;
    white-space: wrap;
    }
  .card {
    gap: 5px;
    width: 240px;
    height: 177px;
    margin-right: 10px;
    display: inline-flex;
    color: #1F1D39;
    background-color: #F5F7F9;
    border-radius: 15px;
    align-items: start;
    justify-content: start;
    flex-direction: column;
    padding: 1.3rem 1rem;
  }
  .card-info{
    display: flex;
    width: 100%;
    justify-content: start;
  }
  /* optional */
  .next-btn, .prev-btn {
      display: inline-flex;
      align-items: center;
      width: 30px;
      height: 30px;
      justify-content: center;
      background-color: black;
      border: 1px solid #E7EAE9;
      padding: 10px 10px;
      border-radius: 100%;
      margin: 0;
      cursor: pointer;
      position: absolute;
      top: 0;
      margin-top: 20%;
      transform: translateY(-50%);

  }
  .next-btn{
    left: 2rem;
  }
  .prev-btn{
      right: 2rem;
  }
  </style>