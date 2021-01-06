<template>
<body>
  <div id="app">
<!-- //lọc dữ liệu sắp xếp tìm kiếm -->
    <!-- <div>{{Loc}}</div> -->
    <!-- <div>{{callapi.data}}</div>
    <div @click="postPost">giangPost</div>
    <div @click="giangput">giangput</div> -->
    <compLeft/>
  <div id="right">
    <CompTop/>
    <CompContent/>
  </div>
    <!-- <CompFilter/> -->
  </div>
</body>
</template>
<script>
// import axios from 'axios'
import compLeft from './components/compLeft'
import CompTop from './components/compRight/compTop'
import CompContent from './components/compRight/compContent'
export default {
  name: 'App',
  components: {
    compLeft,
    CompTop,
    CompContent
  }

  // data () {
  //   return {
  //     giang1: 'fadsf',
  //     callapi: []
  //   }
  // },
  // mounted () {
  //   axios
  //     .get('http://localhost:3000/tasks')
  //     .then(response => (this.callapi = response))
  // },
  // methods: {
  //   hahabackend (e) {
  //     alert(this.callapi)
  //   },
  //   postPost () {
  //     axios.post('http://localhost:3000/tasks', {
  //       name: 'nguyen truong giang post2'
  //     })
  //       .then(response => {})
  //       .catch(e => {
  //         this.errors.push(e)
  //       })
  //   },
  //   giangput () {
  //     // alert('ahihiput')
  //     // axios.put('http://localhost:3000/tasks', +'5ff36cf273f45f21a0ec738d', 'formData', {
  //     //   headers: {
  //     //     'name': 'giang',
  //     //     'Content-Type': 'application/json'
  //     //   }
  //     // })
  //     //   .then(response => {
  //     //     console.log(response.data)
  //     //   })
  //     //   .catch(function (error) {
  //     //     console.log(error)
  //     //   })
  //   }
}
</script>
<style>
#right {
  display: flex;
     flex-direction: column;
    flex: 1;
    margin:0px 5px;
/*
  overflow-y: overlay; */
}
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
