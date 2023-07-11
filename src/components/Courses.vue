<script>
export default {

  name: 'Courses',
  data () {
    return {
      cards: [1, 2, 3, 4, 5, 6, 7, 8, 9],
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
    <h1 class="block-title">Мои курсы</h1>
    <div class="carousel">
      <div class="inner" ref="inner" :style="innerStyles">
        <div class="card" >
          
          <div class="card-stat">
            <div class="stat-icon">
              <img src="@/assets/icon/card1.svg" alt="">
            </div>
            <div class="stat-detail">
              <h1>2/24</h1>
              <p>уроков пройдено</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Название курса</h1>
          </div>
          <div class="card-info">
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/book.svg" />  
              <span>24</span>
            </div>
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/doc.svg" />  
              <span>8</span>
            </div>
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/group.svg" />  
              <span>99</span>
            </div>
          </div>
        </div>
        
        <div class="card" >
          
          <div class="card-stat">
            <div class="stat-icon">
              <img src="@/assets/icon/card1.svg" alt="">
            </div>
            <div class="stat-detail">
              <h1>2/24</h1>
              <p>уроков пройдено</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Название курса</h1>
          </div>
          <div class="card-info">
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/book.svg" />  
              <span>24</span>
            </div>
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/doc.svg" />  
              <span>8</span>
            </div>
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/group.svg" />  
              <span>99</span>
            </div>
          </div>
        </div>
        <div class="card" style="background-color: #F8EFE2;">
          <div class="card-stat">
            <div class="stat-icon">
              <img src="@/assets/icon/graph.svg" alt="">
            </div>
            <div class="stat-detail">
              <h1>2/24</h1>
              <p>уроков пройдено</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Второй курс</h1>
          </div>
          <div class="card-info">
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/book.svg" />  
              <span>24</span>
            </div>
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/doc.svg" />  
              <span>8</span>
            </div>
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/group.svg" />  
              <span>99</span>
            </div>
          </div>
        </div>
        
        <div class="card" style="background-color: #F8EFE2;">
          <div class="card-stat">
            <div class="stat-icon">
              <img src="@/assets/icon/graph.svg" alt="">
            </div>
            <div class="stat-detail">
              <h1>2/24</h1>
              <p>уроков пройдено</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Второй курс</h1>
          </div>
          <div class="card-info">
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/book.svg" />  
              <span>24</span>
            </div>
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/doc.svg" />  
              <span>8</span>
            </div>
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/group.svg" />  
              <span>99</span>
            </div>
          </div>
        </div>
        <div class="card" style="background-color: #EFF7E2;">
            
          <div class="card-stat">
            <div class="stat-icon">
              <img src="@/assets/icon/analytics.svg" alt="">
            </div>
            <div class="stat-detail">
              <h1>2/24</h1>
              <p>уроков пройдено</p>
            </div>
          </div>
          <div class="card-title">
            <h1>Третий курс</h1>
          </div>
          <div class="card-info">
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/book.svg" />  
              <span>24</span>
            </div>
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/doc.svg" />  
              <span>8</span>
            </div>
            <div class="card-info-item">
              <img class="icon" src="@/assets/icon/group.svg" />  
              <span>99</span>
            </div>
          </div>
        </div>
        
        <div class="card" style="background-color: #EFF7E2;">
            
            <div class="card-stat">
              <div class="stat-icon">
                <img src="@/assets/icon/analytics.svg" alt="">
              </div>
              <div class="stat-detail">
                <h1>2/24</h1>
                <p>уроков пройдено</p>
              </div>
            </div>
            <div class="card-title">
              <h1>Третий курс</h1>
            </div>
            <div class="card-info">
              <div class="card-info-item">
                <img class="icon" src="@/assets/icon/book.svg" />  
                <span>24</span>
              </div>
              <div class="card-info-item">
                <img class="icon" src="@/assets/icon/doc.svg" />  
                <span>8</span>
              </div>
              <div class="card-info-item">
                <img class="icon" src="@/assets/icon/group.svg" />  
                <span>99</span>
              </div>
            </div>
          </div>
        <div class="card" style="background-color: #EFF7E2;">
            
            <div class="card-stat">
              <div class="stat-icon">
                <img src="@/assets/icon/analytics.svg" alt="">
              </div>
              <div class="stat-detail">
                <h1>2/24</h1>
                <p>уроков пройдено</p>
              </div>
            </div>
            <div class="card-title">
              <h1>Третий курс</h1>
            </div>
            <div class="card-info">
              <div class="card-info-item">
                <img class="icon" src="@/assets/icon/book.svg" />  
                <span>24</span>
              </div>
              <div class="card-info-item">
                <img class="icon" src="@/assets/icon/doc.svg" />  
                <span>8</span>
              </div>
              <div class="card-info-item">
                <img class="icon" src="@/assets/icon/group.svg" />  
                <span>99</span>
              </div>
            </div>
          </div>
        
          <div class="card" style="background-color: #EFF7E2;">
            
            <div class="card-stat">
              <div class="stat-icon">
                <img src="@/assets/icon/analytics.svg" alt="">
              </div>
              <div class="stat-detail">
                <h1>2/24</h1>
                <p>уроков пройдено</p>
              </div>
            </div>
            <div class="card-title">
              <h1>Третий курс</h1>
            </div>
            <div class="card-info">
              <div class="card-info-item">
                <img class="icon" src="@/assets/icon/book.svg" />  
                <span>24</span>
              </div>
              <div class="card-info-item">
                <img class="icon" src="@/assets/icon/doc.svg" />  
                <span>8</span>
              </div>
              <div class="card-info-item">
                <img class="icon" src="@/assets/icon/group.svg" />  
                <span>99</span>
              </div>
            </div>
          </div>
          <div class="card" style="background-color: #EFF7E2;">
            
            <div class="card-stat">
              <div class="stat-icon">
                <img src="@/assets/icon/analytics.svg" alt="">
              </div>
              <div class="stat-detail">
                <h1>2/24</h1>
                <p>уроков пройдено</p>
              </div>
            </div>
            <div class="card-title">
              <h1>Третий курс</h1>
            </div>
            <div class="card-info">
              <div class="card-info-item">
                <img class="icon" src="@/assets/icon/book.svg" />  
                <span>24</span>
              </div>
              <div class="card-info-item">
                <img class="icon" src="@/assets/icon/doc.svg" />  
                <span>8</span>
              </div>
              <div class="card-info-item">
                <img class="icon" src="@/assets/icon/group.svg" />  
                <span>99</span>
              </div>
            </div>
          </div>
      </div>
    </div>
    <button class="next-btn" @click="prev">
      <img src="@/assets/icon/prev.svg" alt="Image">
    </button>
    <button class="prev-btn" @click="next">
      <img src="@/assets/icon/next.svg" alt="Image">
    </button>
  </div>
    
  </template>
  
  
  <style scoped>
  .wrapper{
    width: 100%;
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
    background-color: white;
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
  .card-stat{
    display: flex;
    align-items: start;
  } .card-stat h1 {
    font-size: 36px;
    font-family: "Gilroy-UltraLight";
  } .card-stat p {
    font-size: 10px;
    color: black;
    opacity: 50%;
    margin-top: -1rem!important;
    }
    .card-title h1{
      font-family: Gilroy;
      font-size: 16px;
      font-weight: 600;
      line-height: 19px;
      letter-spacing: 0em;
      text-align: left;
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
    gap: 10px;
    width: 240px;
    height: 177px;
    margin-right: 10px;
    display: inline-flex;
    background-color: #E1E2F6;
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
    background-color: white;
    border-radius: 11px;
    justify-content: center;
    padding: .7rem 2rem;
    font-family: Gilroy-Bold;
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