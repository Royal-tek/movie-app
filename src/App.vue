<template>
<header>
  <router-link to="/">
    <h1><span>Vue</span>Movies</h1>
  </router-link>
</header>
<main>
  <router-view/>
</main>
<div class="footer">
<div class="footer-bottom">&copy; Protek</div>
</div>
</template>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Fira Sans', sans-serif;

  &::selection{
    background: transparentize(#42bb83, 0.5);
  }
}
body{
  background-color: #35495e;
}
a{
  text-decoration: none;
}
header{
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px 15px;
  background-color: #2c3d4e;
  box-shadow: 0px 0px 0px 6px rgba(0,0,0,0.1);

  h1{
    color: #fff;
    font-size: 28px;
  }
  span{
    color: #42bb83;
  }
}
.footer{
  width: 100%;
  height: 100px;
  position: relative;

  .footer-bottom{
    width: 100%;
    background-color:rgba(0,0,0,0.1) ;
    position: absolute;
    left: 0;
    text-align: center;
    padding: 10px;
    bottom: 0;
    font-size: 18px;
    color: #42bb83;
    height: 50px;
  }
}
</style>
