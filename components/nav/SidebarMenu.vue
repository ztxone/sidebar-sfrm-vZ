<template>
<div class="nav">
  <div class="nav__folder-toggle">Menu</div>
  <nuxt-link
    no-prefetch
    class="nav__item pointer"
    active-class="nav__item--active"
    exact
    to="/"
    @click.native="sidebarVisible = false"
    >
    <div class="nav__icon"></div>
    <div class="nav__text">
      Главная
    </div>
  </nuxt-link>

  <nuxt-link
    no-prefetch
    class="nav__item pointer"
    active-class="nav__item--active"
    to="/distributions"
    @click.native="sidebarVisible = false"
    >
    <div class="nav__icon nav__icon--subtrack"></div>
    <div class="nav__text">
      Дистрибуция
    </div>
  </nuxt-link>

  <!-- <nuxt-link no-prefetch class="nav__item pointer" active-class="nav__item&#45;&#45;active" to="/statistic" @click.native="sidebarVisible=false">
  <div class="nav__icon nav__icon--static"></div>
  <div class="nav__text">
    Статистика
  </div>
  </nuxt-link>-->

  <a class="nav__item pointer" @click="showMessage">
    <div class="nav__icon nav__icon--static"></div>
    <div class="nav__text">Статистика</div>
  </a>

  <a class="nav__item pointer" @click="showMessage">
    <div class="nav__icon nav__icon--multi"></div>
    <div class="nav__text">Мультиссылка</div>
  </a>

  <a class="nav__item pointer" @click="showMessage">
    <div class="nav__icon nav__icon--star"></div>
    <div class="nav__text">События</div>
  </a>

  <hr class="hr-border">
  <div class="nav__folder-toggle pointer" @click="analyticOpen = !analyticOpen">Analytics <span class="btn-arrow" :class="[!analyticOpen ? 'btn-arrow--closed' : '']"><svg width="9" height="6" viewBox="0 0 11 6" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M8.7722 0.272267C9.10702 -0.0887247 9.64965 -0.0887246 9.996 0.260234C10.1692 0.44073 10.25 0.669358 10.25 0.910019C10.25 1.13865 10.1692 1.36727 9.996 1.53574L5.98979 5.73527C5.82815 5.90374 5.60879 6 5.37789 6C5.14698 6 4.92762 5.90374 4.76599 5.73527L0.759769 1.53574C0.41341 1.18678 0.41341 0.621226 0.759769 0.260234C1.09458 -0.0887246 1.64876 -0.0887247 1.98357 0.272267L5.37789 3.82202L8.7722 0.272267Z" fill="#808191"/>
  </svg></span></div>
  <transition name="nav" mode="out-in">
    <div v-show="analyticOpen" class="nav__folder">
      <nuxt-link
        no-prefetch
        class="nav__item pointer"
        active-class="nav__item--active"
        to="/charts"
        @click.native="sidebarVisible = false"
      >
        <div class="nav__icon nav__icon--chart"></div>
        <div class="nav__text">
          Чарты
        </div>
      </nuxt-link>

      <a class="nav__item pointer" @click="showMessage">
        <div class="nav__icon nav__icon--static"></div>
        <div class="nav__text">Топ лейблов</div>
      </a>
    </div>
  </transition>
  <hr class="hr-border">
  <div class="nav__folder-toggle pointer" @click="soundOpen = !soundOpen">Sound Production <span class="btn-arrow" :class="[!soundOpen ? 'btn-arrow--closed' : '']"><svg width="9" height="6" viewBox="0 0 11 6" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M8.7722 0.272267C9.10702 -0.0887247 9.64965 -0.0887246 9.996 0.260234C10.1692 0.44073 10.25 0.669358 10.25 0.910019C10.25 1.13865 10.1692 1.36727 9.996 1.53574L5.98979 5.73527C5.82815 5.90374 5.60879 6 5.37789 6C5.14698 6 4.92762 5.90374 4.76599 5.73527L0.759769 1.53574C0.41341 1.18678 0.41341 0.621226 0.759769 0.260234C1.09458 -0.0887246 1.64876 -0.0887247 1.98357 0.272267L5.37789 3.82202L8.7722 0.272267Z" fill="#808191"/>
  </svg></span></div>
  <transition name="nav" mode="out-in">
    <div v-show="soundOpen" class="nav__folder">
      <nuxt-link
        no-prefetch
        class="nav__item pointer"
        active-class="nav__item--active"
        to="/minuses"
        @click.native="sidebarVisible = false"
      >
        <div class="nav__icon nav__icon--track"></div>
        <div class="nav__text">
          Минуса
        </div>
      </nuxt-link>

      <a class="nav__item pointer" @click="showMessage">
        <div class="nav__icon nav__icon--star"></div>
        <div class="nav__text">Студии</div>
      </a>
    </div>
  </transition>
  <hr class="hr-border">
  <div class="nav__folder-toggle pointer" @click="financeOpen = !financeOpen">Finance <span class="btn-arrow" :class="[!financeOpen ? 'btn-arrow--closed' : '']"><svg width="9" height="6" viewBox="0 0 11 6" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M8.7722 0.272267C9.10702 -0.0887247 9.64965 -0.0887246 9.996 0.260234C10.1692 0.44073 10.25 0.669358 10.25 0.910019C10.25 1.13865 10.1692 1.36727 9.996 1.53574L5.98979 5.73527C5.82815 5.90374 5.60879 6 5.37789 6C5.14698 6 4.92762 5.90374 4.76599 5.73527L0.759769 1.53574C0.41341 1.18678 0.41341 0.621226 0.759769 0.260234C1.09458 -0.0887246 1.64876 -0.0887247 1.98357 0.272267L5.37789 3.82202L8.7722 0.272267Z" fill="#808191"/>
  </svg></span></div>
  <transition name="nav" mode="out-in">
    <div v-show="financeOpen" class="nav__folder">
      <nuxt-link
        no-prefetch
        class="nav__item pointer"
        active-class="nav__item--active"
        to="/partner"
        @click.native="sidebarVisible = false"
      >
        <div class="nav__icon nav__icon--work"></div>
        <div class="nav__text">
          Партнёрка
        </div>
      </nuxt-link>

      <nuxt-link
        no-prefetch
        class="nav__item pointer"
        active-class="nav__item--active"
        to="/finance"
        @click.native="sidebarVisible = false"
      >
        <div class="nav__icon nav__icon--wallet"></div>
        <div class="nav__text">
          Финансы
        </div>
      </nuxt-link>
    </div>
  </transition>
</div>
</template>

<script>
export default {
  data () {
    return {
      sidebarVisible: true,
      analyticOpen: true,
      soundOpen: true,
      financeOpen: true,
    }
  },
  methods: {
        showMessage () {
        this.flashMessage.show({
          status: 'warning',
          message: 'Раздел скоро будет доступен',
        })
      },
  }
}
</script>

<style lang="scss" scoped>
$cubic: cubic-bezier(0.4, 0.01, 0.165, 0.99);

.nav-enter {
  height: 0;
  opacity: 0;
}
.nav-enter-active,
.nav-leave-active {
  -webkit-transition: 0.5s $cubic;
  transition: 0.5s $cubic;
}
.nav-leave {
opacity: 0;
}
.nav-leave-to {
  height: 0;
}

.pointer {
  cursor: pointer;
}
.nav {
  width: 100%;
  padding-bottom: 30px;
  
  &>a,
  &__folder>a {
    color: #d2d2d2;
    text-decoration: none;

    &:hover {
      color: #da9543 !important;      
    }
  }

  &__item {
    display: flex;
    text-decoration: none;
    margin-bottom: 5px;
    padding: 10px 26px;
    transition: all 0.3s ease;
    // transition: border 0.15s ease;
    border-left: 1.5px solid transparent;    

    &:hover,
    &--active {      
      color: #da9543 !important;
      border-left: 1.5px solid #DA9543;
      background: linear-gradient(90deg, rgba(218, 149, 67, 0.25) 0.43%, rgba(25, 25, 25, 0) 100%);
      
      & > .nav__icon {
        background-image: url('assets/icons/main_hover.svg');

        &--subtrack {
          background-image: url('assets/icons/subtract_hover.svg');
        }

        &--static {
          background-image: url('assets/icons/static_hover.svg');
        }

        &--multi {
          background-image: url('assets/icons/multi_hover.svg');
        }

        &--chart {
          background-image: url('assets/icons/chart_hover.svg');
        }

        &--star {
          background-image: url('assets/icons/star_hover.svg');
        }

        &--track {
          background-image: url('assets/icons/track_hover.svg');
        }

        &--work {
          background-image: url('assets/icons/work_hover.svg');
        }

        &--wallet {
          background-image: url('assets/icons/wallet_hover.svg');
        }
      }
    }
  }
  
  &__icon {
    width: 24px;
    height: 24px;
    background-image: url('assets/icons/main.svg');
    background-repeat: no-repeat;
    background-position: center left;
    background-size: contain;
    transition: all 0.5s ease;

    & > svg:hover {
      fill: #da9543 !important;
    }
    &--subtrack {
      background-image: url('assets/icons/subtract.svg');
    }

    &--static {
      background-image: url('assets/icons/static.svg');
    }

    &--multi {
      background-image: url('assets/icons/multi.svg');
    }

    &--chart {
      background-image: url('assets/icons/chart.svg');
    }

    &--star {
      background-image: url('assets/icons/star.svg');
    }

    &--track {
      background-image: url('assets/icons/track.svg');
    }

    &--work {
      background-image: url('assets/icons/work.svg');
    }

    &--wallet {
      background-image: url('assets/icons/wallet.svg');
    }
  }

  &__text {
    margin-left: 17px;
    font-weight: 500;
    font-size: 14px;
    font-style: normal;
    line-height: 24px;
  }

  &__folder-toggle {
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 12px;
    line-height: 20px;
    color: #808191;
    padding: 10px 26px;

    &:hover:not(:first-child) {
      transition: all 0.5s ease;
      color: #da9543 !important;
      
      &>span svg path {
        fill: #DA9543;
      }
    }    
  }
}
.btn-arrow {
  transition: transform .5s ease;
  transform: rotate(180deg);

  &--closed{
    transform: rotate(0deg);
    transition: transform .5s ease;
  }
}

.hr-border {
  width: 100%;
  max-width: 180px;
  height: 1px;
  margin-top: 10px;
  margin-bottom: 10px;
  margin-left: auto;
  margin-right: auto;
  background-color: #242422;
  border: none;
}

// @media (max-width: 868px) {
//   .nav__item {
//     transform: scale(1.15) translateX(-30px);
//     opacity: 0;
//     transition: transform 0.5s $cubic, opacity 0.6s $cubic;

//     @for $i from 1 through 12 {
//       &:nth-child(#{$i}) {
//         transition-delay: #{0.84 - ($i * 0.07)}s;
//       }
//     }
//   }
//   .active {
//     position: fixed;
//     bottom: 0;
//     left: 0;
//     width: 250px;
//     overflow: auto;

//     &::-webkit-scrollbar {
//       display: none;
//     }

//     .nav__item {
//       transform: scale(1) translateX(0);
//       opacity: 1;

//       @for $i from 1 through 12 {
//         &:nth-child(#{$i}) {
//           transition-delay: #{0.14 * $i + 0.2}s;
//         }
//       }
//     }
//   }
// } 
</style>