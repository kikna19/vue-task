<template>
  <div class="container-fluid  main pt-2">
    <div class="row d-flex align-items-center">
      <div class="col-4 d-flex  align-items-">
        <h1>favourite cars</h1>
      </div>
      <div class="col-8 d-flex justify-content-end align-items-center">
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
        document.body.style.overflowY = 'hidden'
      else
        document.body.style.overflowY = 'scroll'
    }
  }

}
</script>


<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Arizonia&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Rubik+Dirt&display=swap');
$border-color: #b964f3;


.main {
  display: inline-block;
  height: 5rem;
  padding: 0 4.3rem 0 4.3rem;
  color: white;
  border-bottom: .1rem solid $border-color;

  .row {
    height: 80% !important;
  }


  h1 {
    font-family: 'Arizonia', cursive;
    text-transform: capitalize;
  }

  a {
    margin-left: 3rem;
    font-family: 'Rubik Dirt', cursive;
    text-transform: capitalize;
    font-size: 1.1rem;
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

    a {
      margin: 2rem 0 0 0;
    }
  }
}

@media (max-width:920px) {
  .main {
    h1 {
      font-size: 1.7rem;
    }

    a {
      margin-left: 2rem;
      font-size: 1rem;
    }
  }
}

@media (max-width:750px) {
  .main {
    h1 {
      font-size: 1.5rem;
    }

    a {
      margin-left: 1rem;
      font-size: 1rem;
    }
  }
}

@media (max-width:680px) {
  .main {
    .col-8 {
      display: none;

      a {
        display: none;
      }
    }

    .col-4 {
      width: auto;
      margin-top: .6rem;
    }

    i {
      position: absolute;
      left: calc(100% - 6.9rem);
      display: block;
      width: auto;
    }
  }
}


@media (max-width:550px) {
  .main {
    padding: 0 1.3rem 0 1.3rem;

    .drop {
      padding-left: 2rem;
    }

    i {
      left: calc(100% - 3.9rem);
    }
  }
}
</style>