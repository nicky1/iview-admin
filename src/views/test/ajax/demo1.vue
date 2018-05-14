<template>
    <Card>
        <Button type="primary" @click="doClick('222')">戳我试试</Button>
        <br><br>
        <Button type="success" @click="doClickA()">再戳我试试，小样</Button>
    </Card>
</template>

<script>
import axios from 'axios';

export default {
  methods:{
      doClick(s) {
          console.log('click23'+s);
          //测试ajax请求
          axios.get('http://localhost:8888/api/test/get?id=3').then(res =>{
              console.log(res.data);

          });
      },
      doClickA(){
          let data={
              amount:10
          };

          axios.post('http://localhost:8888/api/test/post',data).then(res => {
              console.log(res.data);
          })
      }
  }
}
</script>

