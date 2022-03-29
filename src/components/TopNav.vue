<template>
  <header class='top-nav'>
    <!-- <img alt='likemetric logo' src='../assets/likemetric.png' /> -->
    <nav>
    <ul id='navbar'>
      <li v-for='item in items' :key='item.id'> {{ item.list }}</li>
    </ul>
    </nav>
    <button>Text</button>
  </header>
</template>

<script>
export default {
  name: 'TopNav',
  data: function () {
    return {
      items: [
        { list: 'Products' },
        { list: 'Solutions' },
        { list: 'Pricing' },
        { list: 'Insight' },
        { list: 'About Us' },
        { list: 'Industry' }
      ],
      title: 'Signup'
    }
  }
}
</script>

<style>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #fff;
  height: 70px;
}
ul {
  display: flex;
  align-items: center;
  gap: 10px;
  justify-content: center;
}
ul li {
  list-style: none;
}</style>
