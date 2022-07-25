<template>
  <div>
    <component-header :username='user.name'/>
    <div class="sticker-board">
        <component-sticker 
        v-for="(item, i) in stickers" :key="i"
        :titulo="item.titulo" :descripcion="item.desc"/>
        <component-tools-btn/>
    </div>
  </div>
</template>

<script>
import ComponentSticker from '/src/components/StickerComp.vue'
import ComponentHeader from '/src/components/HeaderComp.vue'
import ComponentToolsBtn from '/src/components/ToolsBtnComponent.vue'

export default {
  name: 'App',
  data() {
    return {
      user: {
        name: 'Alvaro',
      },
      stickers: [
        {titulo: 'Tarea1', desc: 'Desc1'},
        {titulo: 'Tarea2', desc: 'Desc2'},
        {titulo: 'Tarea3', desc: 'Desc3'}
        ]
    }
  },
  components: {
    ComponentHeader,
    ComponentSticker,
    ComponentToolsBtn
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
:root {
  --board-bg-color: radial-gradient(
    circle,
    rgba(55,170,158,1) 0%, 
    rgba(1,93,147,1) 100%);
  --header-fnt-color: white;
}

/*Spacing related variables*/
:root {
  --header-height: clamp(40px,8vh,50px);
  --header-btn-space: auto 20px;
}

/*Font-style related variables*/
:root {
  --header-fnt-weight: bold;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: calc(var(--header-height) + 20px) 20px;
  background: var(--board-bg-color);
  height: calc(100vh - calc(var(--header-height) + 20px) * 2);
  max-width: 100%;
  }

  .sticker-board {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1em;
    margin: auto;
    padding: 0 clamp(10px, 5%, 50px);
  }
  @media (min-width:20em) {
    .sticker-board {
      grid-template-columns: repeat(auto-fit, minmax(14em, 1fr));
    }
  }
</style>