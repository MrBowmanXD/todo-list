<template>
  <footer class="Container">
    <div class="MainContainer center FlexEnd">
      <h5>Copyright © 2022 Manuel Gonçalves</h5>
      <div class="GithubIcon">
        <a href="https://github.com/MrBowmanXD" target="blank">
          <i class="fa-brands fa-github"></i>
        </a>
      </div>
    </div>
    <div class="ExtraContainer center FlexStart">
      <h5>This project was inspired by <a href="https://michalosman.github.io/todo-list/">michalosman project</a></h5>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style scoped>
  .Container {
    height: 5vh;
    font-size: 20px;
  }

  h5 {
    font-weight: 300;
  }

  .GithubIcon {
    cursor: pointer;
    margin-left: 10px;
  }

  .GithubIcon a {
    text-decoration: none;
    color: black;
  }

  .FlexEnd {
    align-items: flex-end;
  }

  .FlexStart {
    align-items: flex-start;
  }
</style>
