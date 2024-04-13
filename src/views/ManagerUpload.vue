<template>
  <div class="clearfix" id="full">
    <div id="contentNav">
      <h2>
        <RouterLink to="/">주문관리</RouterLink>
      </h2>
      <h2>
        <RouterLink to="/">상품관리</RouterLink>
      </h2>
    </div>

    <div id="contentMain">
      <div id="graph">
        <p>통계</p>
        <p>여기에 그래프나 데이터 값 넣기</p>
        <canvas ref="MyChart" />
      </div>
      <div class="clearfix">

        <div id="pp">
          <h3>구매진행중</h3>

          <table id="ppp">
            <tbody>
              <tr>
                <td id="img" rowspan="3"><img id="img" src="../assets/logo.png" alt=""></td>
                <td id="word">상품명 :</td>
                <td id="nick" rowspan="3">닉네임</td>
              </tr>
              <tr>
                <td>색상 :</td>
              </tr>
              <tr>
                <td>수량 :</td>
              </tr>
            </tbody>
          </table>
          <table id="ppp">
            <tbody>
              <tr>
                <td id="img" rowspan="3"><img id="img" src="../assets/logo.png" alt=""></td>
                <td id="word">상품명 :</td>
                <td id="nick" rowspan="3">닉네임</td>
              </tr>
              <tr>
                <td>색상 :</td>
              </tr>
              <tr>
                <td>수량 :</td>
              </tr>
            </tbody>
          </table>
        </div>
        <div id="bb">
          <h3 id="bx">구매진행완료</h3>
          <table id="bbb">
            <tbody>
              <tr>
                <td id="img" rowspan="3"><img id="img" src="../assets/logo.png" alt=""></td>
                <td>상품명 :</td>
                <td id="nick" rowspan="3">닉네임</td>
              </tr>
              <tr>
                <td>색상 :</td>
              </tr>
              <tr>
                <td>수량 :</td>
              </tr>
            </tbody>
          </table>
          <table id="bbb">
            <tbody>
              <tr>
                <td id="img" rowspan="3"><img id="img" src="../assets/logo.png" alt=""></td>
                <td>상품명 :</td>
                <td id="nick" rowspan="3">닉네임</td>
              </tr>
              <tr>
                <td>색상 :</td>
              </tr>
              <tr>
                <td>수량 :</td>
              </tr>
            </tbody>
          </table>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
import '@/assets/css/ManagerUpload.css'

import { Chart, registerables } from 'chart.js'
Chart.register(...registerables)

export default {
  data:() => ({
    type: 'doughnut',
    data: {
      labels: [ '총판매량', '총침대', '총쇼파', '총책상'],
      datasets: [{
        label: '집꾸며죠 판매량',
        data: [ 12, 19, 3, 5, 2, 3 ],
        backgroundColor: [
          'rgba(255, 99, 132, 0.2)',
          'rgba(54, 162, 235, 0.2)',
          'rgba(255, 206, 86, 0.2)',
          'rgba(75, 192, 192, 0.2)',
          
        ],
        borderColor: [
          'rgba(255, 99, 132, 1)',
          'rgba(54, 162, 235, 1)',
          'rgba(255, 206, 86, 1)',
          'rgba(75, 192, 192, 1)',
          
        ],
        borderWidth: 1
      }]
    },
    options: {
      scales: {
        y: {
          beginAtZero: true
        }
      }
    }
  }),
  mounted(){
    this.createChart()
  },
  methods:{
    createChart(){
      new Chart(this.$refs.MyChart, {
        type:'bar',
        data:this.data,
        options:this.options
      })

    }
  }

}
</script>
