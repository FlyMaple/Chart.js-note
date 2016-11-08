# Chart.js-note

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Header</title>
    <meta name='viewport' content='width=device-width, initial-scale=1, maximum-scale=1'>
    <!--<link rel="stylesheet" href="http://kenwheeler.github.io/slick/slick/slick-theme.css">-->
    <!--<link rel="stylesheet" href="//cdn.jsdelivr.net/jquery.slick/1.6.0/slick.css">-->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.5.2/animate.min.css">
    <link href="css/font/css.css" rel="stylesheet">
    <link rel="stylesheet" href="css/style.css">
    <script src="//code.jquery.com/jquery-1.11.0.min.js"></script>
    <script src="js/Chart.js"></script>
    <!--<script src="//cdn.jsdelivr.net/jquery.slick/1.6.0/slick.min.js"></script>-->
</head>
<body>
    <div class="wrapper">
        <div class="container">
            <div class="header">
            </div>
            <div class="body">
                <canvas id="myChart" width="400" height="400"></canvas>
            </div>
        </div>
    </div>

    <script>

        //Chart.defaults.global.elements.rectangle.borderSkipped = 'left';
        Chart.defaults.global.animation.duration = 1000;
        Chart.defaults.global.animation.onComplete = function () {
            
        }
        var ctx = document.getElementById("myChart");
        var myChart = new Chart(ctx, {
            //type: 'horizontalBar',
            type: 'bar',
            data: {
                labels: ["Red", "Blue", "Yellow", "Green", "Purple", "Orange"],
                datasets: [{
                    //type: 'bar',
                    label: 'Bar Comp',
                    data: [12, 19, 3, 5, 3, 4],
                    backgroundColor: [
                        'rgba(255, 99, 132, 0.2)',
                        'rgba(54, 162, 235, 0.2)',
                        'rgba(255, 206, 86, 0.2)',
                        'rgba(75, 192, 192, 0.2)',
                        'rgba(153, 102, 255, 0.2)',
                        'rgba(255, 159, 64, 0.2)'
                    ],
                    borderColor: [
                        'rgba(255,99,132,1)',
                        'rgba(54, 162, 235, 1)',
                        'rgba(255, 206, 86, 1)',
                        'rgba(75, 192, 192, 1)',
                        'rgba(153, 102, 255, 1)',
                        'rgba(255, 159, 64, 1)'
                    ],
                    //  阿災
                    borderWidth: 3
                }/*,
                {
                    type: 'line',
                    label: 'Line Comp',
                    data: [12, 19, 3, 5, 2, 3],
                    fill: false,
                    // 曲線彎曲程度
                    lineTension: 0.3,
                    backgroundColor: 'rgba(255, 159, 64, 0.2)',
                    borderColor: 'rgba(255, 159, 64, 1)',
                    // 線段樣式，沒什麼差
                    borderCapStyle: 'butt',
                    // 線段樣式，沒什麼差
                    borderJoinStyle: 'miter',
                    borderDash: [10, 20, 40],
                    borderDashOffset: 20,
                    borderWidth: 1,
                    pointRadius: 5,
                    pointHoverRadius: 5,
                    // 沒什麼差
                    pointHitRadius: 10,
                    pointHoverBackgroundColor: "rgba(75,192,192,1)",
                    pointHoverBorderColor: "rgba(220,220,220,1)",
                    pointHoverBorderWidth: 2,
                    showLine: true,
                    // 不知道
                    spanGaps: true,
                    // 方形線圖
                    steppedLine: false,
                    cubicInterpolationMode: 'monotone'
                }*/]
            },
            options: {
                scales: {
                    xAxes: [
                        {
                            display: false
                        }
                    ],
                    yAxes: [{
                        stacked: true,
                        ticks: {
                            beginAtZero:true
                        }
                    }]
                },
                /* 是否要自適應圖表大小 */
                responsive: true,
                /* 自適應時圖表的動話顯示時間 */
                responsiveAnimationDuration: 3000,
                /* 自適應時圖表的長寬是否等比縮放 */
                maintainAspectRatio: false,
                /* Canvas 範圍內點選的事件 */
                onClick: function () {  
                
                },
                /* 預設 Canvas 所實做的監聽事件 */
                events: ["mousemove", "mouseout", "click", "touchstart", "touchmove", "touchend"],
                /*
                需配合 generateLegend 的樣子，polarArea、doughnut 要特別研究
                legendCallback: function (chart) {
                    console.log(chart);
                },
                */
                /* 圖表變更大小的事件 */
                onResize: function () {
                },
                title: {
                    display: true,
                    text: 'Test',
                    position: 'top',
                    padding: 10,
                    fontColor: '#903aaa',
                    fontFamily: '新細明體',
                    fontSize: 22,   /* 不適用於 radialLinear scale point labels */
                    fontStyle: 'bold',
                },
                legend: {
                    disaply: true,
                    position: 'top',
                    /* 阿災 */
                    fullWidth: true,
                    /* legend點擊事件 */
                    onClick: function (event, legendItem) {
                    },
                    /* legend hover事件 */
                    onHover: function (event, legendItem) {
                        /*
                        legendItem:
                        {
                            "text": "xxx",
                            "fillStyle": "rgba(255, 99, 132, 0.2)",
                            "hidden": false,
                            "lineWidth": 1,
                            "lineCap": undefined,
                            "lineDash": undefined,
                            "lineDashOffset": undefined,
                            "lineJoin": undefined,
                            "pointStyle": undefined,
                            "strokeStyle": [
                                "rgba(255,99,132,1)",
                                "rgba(54, 162, 235, 1)",
                                "rgba(255, 206, 86, 1)",
                                "rgba(75, 192, 192, 1)",
                                "rgba(153, 102, 255, 1)",
                                "rgba(255, 159, 64, 1)"
                            ],
                            "datasetIndex": 0
                        }
                        */;
                    },
                    labels: {
                        boxWidth: 40,
                        fontSize: 22,
                        fontStyle: "normal",
                        fontColor: "#666",
                        fontFamily: "新細明體",
                        padding: 10,
                        /*
                        generateLabels: function (chart) {

                        }
                        */
                        /* legend 變圓形 */
                        usePointStyle: false,
                        /* 阿災 */
                        reverse: false
                    }
                },
                tooltips: {
                    enabled: true,
                    /* 可以自訂 tooltip 樣式&內容 */
                    custom: function (tooltip) {
                        if (!tooltip) {
                            return;
                        }
                    },
                    /* 阿災 */
                    mode: 'single',
                    /*
                    阿災
                    itemSort: function () {
                        
                    }
                    */
                    backgroundColor: 'rgba(0,0,0,.7)',
                    titleFontFamily: "'Helvetica Neue', 'Helvetica', 'Arial', sans-serif",
                    titleFontSize: 12,
                    titleFontStyle: "bold",
                    titleFontColor: "#fff",
                    titleSpacing: 2,
                    titleMarginBottom: 6,
                    bodyFontFamily: "'Helvetica Neue', 'Helvetica', 'Arial', sans-serif",
                    bodyFontSize: 12,
                    bodyFontStyle: "normal",
                    bodyFontColor: "#fff",
                    bodySpacing: 2,
                    footerFontFamily: "'Helvetica Neue', 'Helvetica', 'Arial', sans-serif",
                    footerFontSize: 12,
                    footerFontStyle: "bold",
                    footerFontColor: "#fff",
                    footerSpacing: 2,
                    footerMarginTop: 6,
                    xPadding: 6,
                    yPadding: 6,
                    cornerRadius: 6,
                    /* 阿災 */
                    multiKeyBackground: "#903aaa"/*,
                    好像也可以客製 tooltip
                    callbacks: {
                        beforeTitle: function () {
                            return '123'
                        }
                    }
                    */
                },
                hover: {
                    /* single、label、x-axis、dataset */
                    mode: 'single',
                    animationDuration: 3000,
                    /* 移動到資料元素上才有物件 */
                    onHover: function () {
                        
                    }
                }
            }
        });
    </script>
</body>
</html>
```
