<template>
    <div class='color'>
        <h1>Battle Bots</h1>

<button @click = 'toggleCreate'>Create</button>
<button @click = 'toggleCollection'>Collection</button>

          <section v-if='showCreate'>
            <form @submit.prevent='addNewBot'>
                <p><input placeholder='Bot Name'></p>
                <p><input placeholder='Attack Value'></p>        
                <p><input placeholder='Health Value'></p>
                  <button>Submit</button>
                  <button>Clear</button>
            </form>
          </section>

          <section v-else>
            <h3>Collection</h3>
            
          </section>

    </div>
</template>




<script>
import Bot from './components/Bot'
export default {
  data (){
    return {
      bots: [{id: 1, bot:'Katrina', attack: 10, health: 50}],
      id: 1,
      showCreate: true,
      name: '',
      attack: '',
      health: ''
    };
  },

  methods: {
    toggleCreate(){
      this.showCreate = true;
    },
    toggleCollection(){
      this.showCreate = false;
    },
    addNewBot(){
      this.id++;
      let newRobot = {
        id: this.id,
        bot: this.name,
        attack: this.attack,
        health: this.health
      };
      this.bots.push(newRobot);
      this.name = '';
      this.attack = '';
      this.health = '';
      this.toggleCollection();
    }
  },
  components: {
    Bot: Bot
  }
}
</script>

<style scoped>
.color {
  background-color: #48D584;
  background-size: cover;
  text-align: center;
  }
</style>
