<!DOCTYPE html>
<html>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.9.4/Chart.js"></script>
<body>
<canvas id="myChart" style="width:100%;max-width:700px"></canvas>

<script>


const dataset =  ['10','1d0','1e0','10','3','5','45','10','65','2','10'];

const vaA = dataset.filter(checkAdult).length;

var xyValues = [
  {x:10, y:2},
  {x:20, y:vaA},
  {x:26, y:1.5}
];

new Chart("myChart", {
  type: "scatter",
  data: {
    datasets: [{
      pointRadius: 4,
      pointBackgroundColor: "rgb(0,0,255)",
      data: xyValues
    }]
  },
  options: {
    legend: {display: false},
    scales: {
      xAxes: [{ticks: {min: 10, max:40}}],
      yAxes: [{ticks: {min: 1, max:4}}],
    }
  }
});

function checkAdult(age) {
  return age == "10";
}
</script>

</body>
</html>


