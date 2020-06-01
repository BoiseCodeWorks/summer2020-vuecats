<template>
  <div class="home container-fluid">
    <div class="row">
      <div class="col-12">
        <img class="text-center" :src="`https://robohash.org/${newCatName}/?set=set4`" />
        <form @submit.prevent="createCat">
          <input type="text" placeholder="Cat Name..." v-model="newCatName" />
          <button class="btn btn-success" type="submit">+</button>
        </form>
      </div>
      <div
        class="kitten col-3"
        :class="{'bg-danger': kitten.pets > kitten.tolerance}"
        v-for="kitten in kittens"
        :key="kitten.name"
      >
        <img class="text-center" :src="kitten.img + kitten.name + '/?set=set4'" />
        <div class>
          <h4 class>{{kitten.name}}</h4>
          <p class>Pets: {{kitten.pets}}</p>
          <button
            type="button"
            class="btn btn-primary"
            @click="kitten.pets++"
            v-if="kitten.pets <= kitten.tolerance"
          >Pet</button>
          <button type="button" class="btn btn-success" @click="kitten.pets=0" v-else>CatNip</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      // local state
      kittens: [{
        name: "Mr. Snibbley",
        img: `https://robohash.org/`,
        pets: 0,
        tolerance: Math.floor(Math.random() * 5)
      }, {
        name: "Ted",
        img: `https://robohash.org/`,
        pets: 0,
        tolerance: Math.floor(Math.random() * 5)
      }],
      newCatName: '',
    }
  },
  methods: {
    createCat() {
      this.kittens.push({
        name: this.newCatName,
        img: `https://robohash.org/`,
        pets: 0,
        tolerance: Math.floor(Math.random() * 5)
      })
      this.newCatName = ''
    }
  }
}
</script>


<style scoped>
  h1 {
    color: aqua;
  }
  .kitten img {
    width: 150px
  }
</style>