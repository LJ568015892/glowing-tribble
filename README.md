# glowing-tribble
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width,height=device-height">
    <title>基础折线图</title>
    <style>::-webkit-scrollbar{display:none;}html,body{overflow:hidden;height:100%;margin:0;}</style>
</head>
<body>
<div id="mountNode"></div>
<script>/*Fixing iframe window.innerHeight 0 issue in Safari*/document.body.clientHeight;</script>
<script src="https://gw.alipayobjects.com/os/antv/pkg/_antv.g2-3.5.1/dist/g2.min.js"></script>
<script src="https://gw.alipayobjects.com/os/antv/pkg/_antv.data-set-0.10.1/dist/data-set.min.js"></script>
<script>
  var data = [{
    year: '1991',
    value: 3
  }, {
    year: '1992',
    value: 4
  }, {
    year: '1993',
    value: 3.5
  }, {
    year: '1994',
    value: 5
  }, {
    year: '1995',
    value: 4.9
  }, {
    year: '1996',
    value: 6
  }, {
    year: '1997',
    value: 7
  }, {
    year: '1998',
    value: 9
  }, {
    year: '1999',
    value: 13
  }];
  var chart = new G2.Chart({
    container: 'mountNode',
    forceFit: true,
    height: window.innerHeight
  });
  chart.source(data);
  chart.scale('value', {
    min: 0
  });
  chart.scale('year', {
    range: [0, 1]
  });
  chart.tooltip({
    crosshairs: {
      type: 'line'
    }
  });
  chart.line().position('year*value');
  chart.point().position('year*value').size(4).shape('circle').style({
    stroke: '#fff',
    lineWidth: 1
  });
  chart.render();
</script>
</body>
</html>
