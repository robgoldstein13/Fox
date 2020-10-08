<template>
  <div class="hp-char">
    <h1>Harry Potter Characters</h1>
    <ul>
      <li v-for="char in characters" :key="char.name">
        <img :src="char.image" alt="Picture of char.name"/>
        <div>
          <h2>{{ char.name }}</h2>
          <dl v-if="char.house">
            <dt>House:</dt><dd>{{char.house}}</dd>
            <dt>Wand:</dt><dd>{{char.wand.core}}</dd>
          </dl>
          <dl v-else>
            <dt>Actor:</dt><dd>{{char.actor}}</dd>
            <dt>Hair Color:</dt><dd>{{char.hairColour}}</dd>
          </dl>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Characters",
  props: {
    characters: Array
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
   list-style: none;
}

li {
  display: flex;
  margin-bottom: 1rem;
  justify-content: center;
  padding-bottom: 1rem;
  border-bottom: 1px solid #000;
  
}
li > div {
  display: flex;
  flex-direction: column;
  width: 30%;
  padding: 0 10px;
}
img {
  width: 10%;
}
h2 { 
  margin-top: 0;
}
dt { 
  float: left;  
  font-weight: bold; 
  margin-right: 5px;
}

dl {
  text-align: justify;
}

@media screen and (max-width: 767px) {
  ul{ padding: 0.5rem}
  li > div {
    width: 100%;
  }
  img {
    width: 50%;
  }
  dt {
    float: none;
  }
  dd {
    margin-left: 0;
    margin-bottom: 1rem;
  }
}
</style>
