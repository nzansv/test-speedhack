<script>
export default {

  name: 'HomeTasks',
  data () {
    return {
      cards: [1, 2, 3, 4, 5, 6, 7, 8],
      innerStyles: {},
      step: '',
      transitioning: false
    }
  },

  mounted () {
    this.setStep()
    this.resetTranslate()
  },

  methods: {
    setStep () {
      const innerWidth = this.$refs.inner.scrollWidth
      const totalCards = this.cards.length
      this.step = `${innerWidth / totalCards}px`
    },

    next () {
      if (this.transitioning) return

      this.transitioning = true

      this.moveLeft()

      this.afterTransition(() => {
        const card = this.cards.shift()
        this.cards.push(card)
        this.resetTranslate()
        this.transitioning = false
      })
    },

    prev () {
      if (this.transitioning) return

      this.transitioning = true

      this.moveRight()

      this.afterTransition(() => {
        const card = this.cards.pop()
        this.cards.unshift(card)
        this.resetTranslate()
        this.transitioning = false
      })
    },

    moveLeft () {
      this.innerStyles = {
        transform: `translateX(-${this.step})
                    translateX(-${this.step})`
      }
    },

    moveRight () {
      this.innerStyles = {
        transform: `translateX(${this.step})
                    translateX(-${this.step})`
      }
    },

    afterTransition (callback) {
      const listener = () => {
        callback()
        this.$refs.inner.removeEventListener('transitionend', listener)
      }
      this.$refs.inner.addEventListener('transitionend', listener)
    },

    resetTranslate () {
      this.innerStyles = {
        transition: 'none',
        transform: `translateX(-${this.step})`
      }
    }
  }
}
</script>
<template>
  <div class="wrapper">
    <h1 class="block-title">Домашние задания</h1>
    <div class="carousel">
      <div class="inner" ref="inner" :style="innerStyles">
        <div class="card" style="border: 2px solid #FFDBC7;">
          
          <div class="card-stat">
            <div class="stat-icon" style="background-color:  #FFDBC7;">
              <img src="@/assets/icon/graph-fill.svg" alt="">
            </div>
            <div class="stat-detail">
              <h1>Домашнее задание №11</h1>
              <p>Второй курс, География</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Сделать до 12 июля</h1>
          </div>
          <div class="card-info">
            <button  class="btn"><span>Открыть задание</span> <img src="@/assets/icon/arrow.svg" alt=""></button>
          </div>
        </div>
        
        <div class="card" style="border: 2px solid #E1E2F6;" >
          
          <div class="card-stat"  >
            <div class="stat-icon" style="background-color: #E1E2F6;">
              <img src="@/assets/icon/card1.svg" alt="">
            </div>
            <div class="stat-detail">
              <h1>Тип данных bool в Java...</h1>
              <p>Первый курс</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Сделать до 12 июля</h1>
          </div>
          <div class="card-info">
            <button style="background-color: #353297;" class="btn"><span>Открыть задание</span> <img src="@/assets/icon/arrow.svg" alt=""></button>
          </div>
        </div>
        <div class="card" style="border: 2px solid #B4D6A4;">
          <div class="card-stat" >
            <div class="stat-icon"  style="background-color: #B4D6A4;">
              <img src="@/assets/icon/analytics-fill.svg" alt="">
            </div>
            <div class="stat-detail">
              <h1>Изучение системы отс...</h1>
              <p>Третий курс</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Сделать до 12 июля</h1>
          </div>
          <div class="card-info">
            <button style="background-color: #82B86F;" class="btn"><span>Открыть задание</span> <img src="@/assets/icon/arrow.svg" alt=""></button>
          </div>
        </div>
        <div class="card" style="border: 2px solid #E1E2F6;" >
          
          <div class="card-stat"  >
            <div class="stat-icon" style="background-color: #E1E2F6;">
              <img src="@/assets/icon/card1.svg" alt="">
            </div>
            <div class="stat-detail">
              <h1>Тип данных bool в Java...</h1>
              <p>Первый курс</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Сделать до 12 июля</h1>
          </div>
          <div class="card-info">
            <button style="background-color: #353297;" class="btn"><span>Открыть задание</span> <img src="@/assets/icon/arrow.svg" alt=""></button>
          </div>
        </div>
        <div class="card" style="border: 2px solid #B4D6A4;">
          <div class="card-stat" >
            <div class="stat-icon"  style="background-color: #B4D6A4;">
              <img src="@/assets/icon/analytics-fill.svg" alt="">
            </div>
            <div class="stat-detail">
              <h1>Изучение системы отс...</h1>
              <p>Третий курс</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Сделать до 12 июля</h1>
          </div>
          <div class="card-info">
            <button style="background-color: #82B86F;" class="btn"><span>Открыть задание</span> <img src="@/assets/icon/arrow.svg" alt=""></button>
          </div>
        </div>
        <div class="card" style="border: 2px solid #9FD6FF;">
          <div class="card-stat" >
            <div class="stat-icon"  style="background-color: #9FD6FF;">
              <img src="@/assets/icon/card1-blue.svg" alt="">
            </div>
            <div class="stat-detail">
              <h1>Изучение системы отс...</h1>
              <p>Третий курс</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Сделать до 12 июля</h1>
          </div>
          <div class="card-info">
            <button class="btn" style="background-color: #0092FF;"><span>Открыть задание</span> <img src="@/assets/icon/arrow.svg" alt=""></button>
          </div>
        </div>
        
        <div class="card" style="border: 2px solid #9FD6FF;">
          <div class="card-stat" >
            <div class="stat-icon"  style="background-color: #9FD6FF;">
              <img src="@/assets/icon/card1-blue.svg" alt="">
            </div>
            <div class="stat-detail">
              <h1>Изучение системы отс...</h1>
              <p>Третий курс</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Сделать до 12 июля</h1>
          </div>
          <div class="card-info">
            <button class="btn" style="background-color: #0092FF;"><span>Открыть задание</span> <img src="@/assets/icon/arrow.svg" alt=""></button>
          </div>
        </div>
        
        <div class="card" style="border: 2px solid #9FD6FF;">
          <div class="card-stat" >
            <div class="stat-icon"  style="background-color: #9FD6FF;">
              <img src="@/assets/icon/card1-blue.svg" alt="">
            </div>
            <div class="stat-detail">
              <h1>Изучение системы отс...</h1>
              <p>Третий курс</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Сделать до 12 июля</h1>
          </div>
          <div class="card-info">
            <button class="btn" style="background-color: #0092FF;"><span>Открыть задание</span> <img src="@/assets/icon/arrow.svg" alt=""></button>
          </div>
        </div>
      </div>
    </div>
    <button class="next-btn" >
      <img src="@/assets/icon/prev.svg" alt="Image">
    </button>
    <button class="prev-btn" >
      <img src="@/assets/icon/next.svg" alt="Image">
    </button>
  </div>
    
  </template>
  
  <style scoped>
  .wrapper{
    width: 100%;
  }
  .btn {
    border: none;
    width: 190px;
    height: 44px;
    border-radius: 10px;
    font-family: "Gilroy";
    background-color: #FF9053;
    color: white;
    cursor: pointer;
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
  .stat-icon{
    min-width: 50px;
    min-height: 50px;
    border-radius: 100%;
    text-align: center;
    margin-top: 5px;
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
      font-size: 13px;
      color: #F94874;
      text-align: center;
    }
    .card-info-item {
      display: flex;
      align-items: center;
      text-align: center;
      gap: 10px;
      border-left: 2px solid #EDEDFB;
      padding: 0 .6rem;
      border-right: 2px solid #EDEDFB;
    } :first-child {
      border-left: none;
    }
      :last-child{
      border-right: none;
    }
  .card {
    gap: 5px;
    width: 240px;
    height: 177px;
    margin-right: 10px;
    display: inline-flex;
    color: #1F1D39;
    border-radius: 15px;
    align-items: start;
    justify-content: start;
    flex-direction: column;
    padding: 1.3rem 1rem;
  }
  .card-info{
    display: flex;
    width: 100%;
    justify-content: center;
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
      margin-top: 40%;
      transform: translateY(-50%);

  }
  .next-btn{
    left: 2rem;
  }
  .prev-btn{
    right: 2rem;
  }
  </style>