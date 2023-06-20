---
layout: post
title: testing
date: 2023-06-18
categories: fiction
author: Saranga Sudarshan
---
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.3.0/chart.min.js" integrity="sha512-mlz/Fs1VtBou2TrUkGzX4VoGvybkD9nkeXWJm3rle0DPHssYYx4j+8kIS15T78ttGfmOjH0lLaBXGcShaVkdkg==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
<!-- <div style="width: 500px;"><canvas id="dimensions"></canvas></div><br/> -->
<div style="width: 800px;"><canvas id="graph" height="350" width="580"></canvas></div>

<!-- <script type="module" src="dimensions.js"></script> -->
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
  var chrt = document.getElementById('acquisitions');
  var graph = new Chart(chrt
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
