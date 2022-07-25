<template>
  <div class="header">
    <header>
      <nav>
        <a href="">Inicio</a>
        <a href="">Acerca de</a>
      </nav>
      <div class="h-user-area">
        <p>{{username}}</p>
      </div>
    </header> 
    <div class="hover-area">

    </div>   
  </div>
</template>

<script>
export default {
  props: {
    username: String,
  }
}
</script>

<style>
.header {
  max-width: 100vw;
  min-height: calc(var(--header-height) * 2);  
  display: flex;
  flex-direction: column;
  position: absolute;
  top: calc(var(--header-height) * -1);
  left: 0;
  transition: 0.3s ease-in-out 2s;
}
header {
  width: 100vw;
  height: var(--header-height);
  background: rgb(182,0,87);
  background: linear-gradient(0deg, rgba(182,0,87,1) 1%, rgba(159,0,109,1) 100%);
  box-shadow:
  0px 2.8px 2.2px rgba(0, 0, 0, 0.02),
  0px 6.7px 5.3px rgba(0, 0, 0, 0.028),
  0px 12.5px 10px rgba(0, 0, 0, 0.035),
  0px 22.3px 17.9px rgba(0, 0, 0, 0.042),
  0px 41.8px 33.4px rgba(0, 0, 0, 0.05),
  0px 100px 80px rgba(0, 0, 0, 0.07);
  display: flex;
  justify-content: space-between;
}
nav {
  display: flex;
}
header a {
  color: var(--header-fnt-color);
  text-decoration: none;
  margin: var(--header-btn-space);
  font-weight: var(--header-fnt-weight);
}
.hover-area {
  min-height: var(--header-height);
}

.header:hover {
  transform: translateY(var(--header-height));
  transition: 0.3s ease-in-out 0.2s;
}
.h-user-area {
  margin: var(--header-btn-space);
}
.h-user-area p {
  color: var(--header-fnt-color);
  font-weight: var(--header-fnt-weight);
}
</style>