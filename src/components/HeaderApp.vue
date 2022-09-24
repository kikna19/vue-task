<template>
  <div class="container-fluid main">
    <h1 class="col-4">favourite cars</h1>
    <div class="col d-flex justify-content-end">
      <a>home</a>
      <a>gallery</a>
      <a>about us</a>
      <a>contact</a>
    </div>
    <i @click="menu" class="bi bi-list-ul"></i>
    <div v-if="drop" class="container-fluid d-flex flex-column drop">
      <a>home</a>
      <a>gallery</a>
      <a>about us</a>
      <a>contact</a>
    </div>
  </div>
</template>
<script>



export default {
  name: 'HeaderApp',
  data() {
    return {
      drop: false,
    }
  },
  methods: {
    menu() {
      this.drop = !this.drop;
      if (this.drop)
        document.body.style.overflow = 'hidden'
      else
        document.body.style.overflow = 'scroll'
    }
  }

}
</script>


<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Arizonia&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Rubik+Dirt&display=swap');
$border-color: #b964f3;

@mixin flex($align, $justify, $dir) {
  display: flex;
  align-items: $align;
  justify-content: $justify;
  flex-direction: $dir;
}


.main {
  @include flex(center, space-between, row);
  height: 5rem;
  padding: 0 5rem 0 5rem;
  color: white;
  border-bottom: .1rem solid $border-color;

  h1 {
    font-family: 'Arizonia', cursive;
    text-transform: capitalize;
  }

  a {
    margin-left: 3rem;
    font-family: 'Rubik Dirt', cursive;
    text-transform: capitalize;
    font-size: 1.2rem;
  }

  i {
    display: none;
    font-size: 2rem;
    cursor: pointer;
  }

  .drop {
    position: absolute;
    top: 5rem;
    left: 0;
    padding-left: 5rem;
    height: calc(100% - 5rem);
    background: rgb(32, 33, 36);
    z-index: 1000;
    transition: 1s all ease-in-out;

    a {
      margin: 2rem 0 0 0;
    }
  }
}

@media (max-width:920px) {
  .main {
    h1 {
      font-size: 1.8rem;
    }

    a {
      margin-left: 2rem;
      font-size: 1rem;
    }
  }
}

@media (max-width:750px) {
  .main {
    a {
      margin-left: 1rem;
    }
  }
}

@media (max-width:680px) {
  .main {
    .col {
      display: none;

      a {
        display: none;
      }
    }

    .col-4 {
      width: auto;
    }

    i {
      display: block;
    }
  }
}


@media (max-width:550px) {
  .main {
    padding: 0 2rem 0 2rem;

    .drop {
      padding-left: 2rem;
    }
  }
}
</style>