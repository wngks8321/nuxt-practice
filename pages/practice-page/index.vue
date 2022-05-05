<template>
  <div>
    <button ref='button1' type='button' class='btn_common btn_small' v-on:click='handleClick'>
      버튼1
    </button>
    <button ref='button2' type='button' class='btn_common btn_medium'>
      버튼2
    </button>
    <button ref='button3' type='button' class='btn_common btn_large'>
      버튼3
    </button>
    <div class="wrap_image" :class="isHover ? 'hover' : ''">
      <!-- <img src="https://images.ctfassets.net/hrltx12pl8hq/5GaLeZJlLyOiQC4gOA0qUM/a0398c237e9744ade8b072f99349e07a/shutterstock_152461202_thumb.jpg?fit=fill&w=480&h=270" alt=""> -->
      <button type="button" class="btn_plus" @mouseover="handleMouseOver" @mouseleave="handleMouseLeave">버튼</button>
    </div>
  
  </div>
</template>

<script>
export default {
  name: 'practice-page',
  data() {
    return { isHover: false }
  },
  methods: {
    handleClick() {
      console.log('test');
    },
    addActiveClass() {
      this.$refs.button1.classList.add('active');
      this.$refs.button2.classList.add('active');
      this.$refs.button3.classList.add('active');
    },
    handleMouseOver() {
      this.isHover = !this.isHover;
    },
    handleMouseLeave() {
      this.isHover = !this.isHover;
    }
  },
  beforeUnmount() {
    // this.$nextTick(function () {
      this.addActiveClass();
    // });
  }
}
</script>

<style lang="scss" scope>
  .active {
    transform: scale(1);
    transition: 1s;
  }

  .wrap_image {
    position: relative;
    width: 400px;
    height: 300px;
    background: powderblue;

    &.hover {
      background: tan;
    }

    .btn_plus {
      position: absolute;
      bottom: 20px;
      right: 20px;
    }
  }
</style>