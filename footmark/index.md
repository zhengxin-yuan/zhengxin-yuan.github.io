# 足迹

## 中国
<div id="yuanzhx-map" style="height: 600px; background-color: transparent;"></div>
<script>
    $('#yuanzhx-map').vectorMap({
		map: 'cn_merc_en',
	    backgroundColor: 'transparent',
		zoomMin: 1,
		zoomMax: 3,
		focusOn: {
			x: 0.55,
			y: 2,
			scale: 1
		},
		regionStyle: {
			initial: {
				fill: '#d3d3d3',   
				"fill-opacity": 1,
				stroke: 'none',
				"stroke-width": 0,
				"stroke-opacity": 1
			},
			hover: {
				fill: '#FF0000',  
				"fill-opacity": 1
			},
			selected: {
				fill: '#0000ff'
			},
			selectedHover: {}
		},		
		markerStyle: {
			initial: {
				fill: '#0000ff',
				stroke: '#fff' ,
				r: 4
			},
			hover: {
				fill: '#0000ff',
				stroke: '#fff',  
				"fill-opacity": 1
			},
		},		
		series: {
			regions: [{
				scale: ['#d3d3d3', '#FFC0CB'],
				normalizeFunction: 'polynomial',
				values: {
					"CN-32": 100,
					"CN-50": 100,
					"CN-36": 100,
					"CN-51": 100,
					"CN-33": 100,
					"CN-31": 100,
					"CN-12": 100,
					"CN-11": 100,
					"CN-34": 100,
					"CN-41": 100,
					"CN-42": 100,
					"CN-45": 100,
					"CN-44": 100,
					"CN-35": 100
				}
			}]
		},		
		markers: [
			{ latLng: [23.10, 113.33], name: 'Guangzhou-2012' },
			{ latLng: [39.12, 117.21], name: 'Tianjin-2015' },
			{ latLng: [39.90, 116.40], name: 'Beijing-2015' },
			{ latLng: [28.68, 115.85], name: 'Nanchang-1994' },
			{ latLng: [29.55, 106.46], name: 'Chongqing-2016' },
			{ latLng: [34.24, 117.18], name: 'Xuzhou-2012' },
			{ latLng: [32.07, 118.74], name: 'Nanjing-2017' },
			{ latLng: [32.46, 119.91], name: 'Taizhou-2017' },
			{ latLng: [24.46, 118.09], name: 'Xiamen-2013' },
			{ latLng: [25.27, 110.30], name: 'Guilin-2012' },
			{ latLng: [32.13, 114.09], name: 'Xinyang-2016' },
			{ latLng: [31.84, 117.26], name: 'Hefei-2016' },
			{ latLng: [30.53, 114.29], name: 'Wuhan-2016' },
			{ latLng: [30.27, 120.15], name: 'Hangzhou-2010' },
			{ latLng: [30.65, 104.07], name: 'Chengdu-2018' },
			{ latLng: [22.33, 114.26], name: 'Hongkong-2020' },
			{ latLng: [22.58, 114.26], name: 'Shenzhen-2012' },
			{ latLng: [31.20, 121.56], name: '2020年上海ChinaJoy' }
		]		
    });
</script>

