---
layout: post
title: testing
date: 2023-06-18
categories: fiction
author: Saranga Sudarshan
---
<div>
<canvas id="graph"></canvas>
</div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.3.0/chart.umd.min.js" integrity="sha512-TJ7U6JRJx5IpyvvO9atNnBzwJIoZDaQnQhb0Wmw32Rj5BQHAmJG16WzaJbDns2Wk5VG6gMt4MytZApZG47rCdg==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>

<script>
  const data = [
    { year: 2010, count: 10 },
    { year: 2011, count: 20 },
    { year: 2012, count: 15 },
    { year: 2013, count: 25 },
    { year: 2014, count: 22 },
    { year: 2015, count: 30 },
    { year: 2016, count: 28 },
  ];
  var chrt = document.getElementById('graph');
  new Chart(chrt
    ,
    {
      type: 'bar',
      data: {
        labels: data.map(row => row.year),
        datasets: [
          {
            label: 'Acquisitions by year',
            data: data.map(row => row.count)
          }
        ]
      }
    }
  );
</script>

