<template>
<body>
  <div id="app">
<!-- //lọc dữ liệu sắp xếp tìm kiếm -->
    <!-- <div>{{Loc}}</div> -->
    <compLeft/>
    <compRight/>
    <compCreateUnion
    />
    <!-- <CompFilter/> -->
  </div>
</body>
</template>
<script>
import compLeft from './components/compLeft'
import compRight from './components/compRight'
import compCreateUnion from './components/compCreateUnion'
import compFilter from './components/compFilter'
export default {
  name: 'App',
  components: {
    compLeft,
    compRight,
    compCreateUnion,
    compFilter
  }
}
</script>
<style>
#app {
  margin: 0px;
  padding: 0px;
  position: relative;
  display: flex;
}
body {
  margin: 0px;
  padding: 0px;
  position: relative;
}
</style>
