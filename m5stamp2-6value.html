<!doctype html>
<!--
Copyright 2017-2020 JellyWare Inc. All Rights Reserved.
-->
<html>
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="description" content="BlueJelly">
    <meta name="viewport" content="width=640, maximum-scale=1.0, user-scalable=yes">
    <title>BlueJelly-ESP32  BLE DEMO</title>
    <link href="https://fonts.googleapis.com/css?family=Lato:100,300,400,700,900" rel="stylesheet" type="text/css">
    <link rel="stylesheet" href="style.css">
    <script type="text/javascript" src="bluejelly.js"></script>
    <script type="text/javascript" src="./smoothie.js"></script>
  </head>

<body>
<div class="container">
    <div class="title margin">
        <h4><p id="title" style="color:blue;">Analog Plot</p></h4>
    </div>

    <div class="contents margin">
        <button id="startNotifications" class="button" style="background-color:fuchsia;">Start M5-1</button>
        <button id="stopNotifications" class="button" style="background-color:fuchsia;">Stop M5-1</button>
        <button id="startNotifications2" class="button" style="background-color:skyblue;">Start M5-2</button>
        <button id="stopNotifications2" class="button" style="background-color:skyblue;">Stop M5-2</button>
        
		<!--<input id="write_value" class="button" value="up" size="20">
        <button id="write" class="button">Write</button>-->
        <hr>
        <div id="svg">GRAPH AREA</div>
        <hr>
        
        <font face="Comic Sans MS" color="#448aff"><span id="data_box0"> </span>
        <span id="data_box0"> </span>
        <span>　</span>
        <span id="data_box1"> </span>
        <span>　</span>
        <span id="data_box2"> </span>
        <span>　</span>
        <span id="data_box3"> </span>
        <span>　</span>
        <span id="data_box4"> </span>
        <span>　</span>
        <span id="data_box5"> </span>
        <span>　</span>
        <span id="data_box6"> </span>
        <span>　</span></font>
        <!--<div id="device_name"> </div>
        <div id="uuid_name"> </div>
        
        <div id="status"> </div>-->

    </div>
    <!--<div class="footer margin">
                For more information, see <a href="https://jellyware.jp/kurage" target="_blank">jellyware.jp</a> and <a href="https://github.com/electricbaka/bluejelly" target="_blank">GitHub</a> !
    </div>-->
</div>


<script>
//--------------------------------------------------
//Global変数
//--------------------------------------------------
//BlueJellyのインスタンス生成
const ble = new BlueJelly();
const ble2 = new BlueJelly();

const ble3 = new BlueJelly();
const ble4 = new BlueJelly();

//TimeSeriesのインスタンス生成
const ble_data = new TimeSeries();



var array1 = new Array(100);
for(let i=0;i<100;i++){
	array1[i] = new Array(6);
}


let startflag1=0;
let startflag2=0;
var M5sen1_val = new Array(3);
var M5sen2_val = new Array(3);

let cyc1=0;
let cyc2=3;




//-------------------------------------------------
//smoothie.js
//-------------------------------------------------
function createTimeline() {
    const chart = new SmoothieChart({
        millisPerPixel: 20,
        grid: {
            fillStyle: '#ff8319',
            strokeStyle: '#ffffff',
            millisPerLine: 800
        },
        maxValue: 5000,
        minValue: 0
    });
    chart.addTimeSeries(ble_data, {
        strokeStyle: 'rgba(255, 255, 255, 1)',
        fillStyle: 'rgba(255, 255, 255, 0.2)',
        lineWidth: 4
    });
    chart.streamTo(document.getElementById("chart"), 500);
}


//--------------------------------------------------
//ロード時の処理
//--------------------------------------------------
window.onload = function () {
  //UUIDの設定
  ble.setUUID("UUID1","4fafc201-1fb5-459e-8fcc-c5c9c331914b","beb5483e-36e1-4688-b7f5-ea07361b26a8");
  ble2.setUUID("UUID1","4fafc201-1fb5-459e-8fcc-c5c9c331914b","2049779d-88a9-403a-9c59-c7df79e1dd7c");

  ble3.setUUID("UUID1","a261407b-14f6-4510-86ed-ddeab74297fb","ea7964b4-0681-4328-b5da-4ef3738dec01");
  ble4.setUUID("UUID1","a261407b-14f6-4510-86ed-ddeab74297fb","0cd118be-e194-4059-a922-c3c91f13c05c");
  
  //smoothie.js
  //createTimeline();
  
  main();
}


//--------------------------------------------------
//Scan後の処理
//--------------------------------------------------
ble.onScan = function (deviceName) {
  //document.getElementById('device_name').innerHTML = deviceName;
  document.getElementById('status').innerHTML = "found device!";
}


//--------------------------------------------------
//ConnectGATT後の処理
//--------------------------------------------------
ble.onConnectGATT = function (uuid) {
  console.log('> connected GATT!');

  //document.getElementById('uuid_name').innerHTML = uuid;
  //document.getElementById('status').innerHTML = "connected GATT!";
}


//--------------------------------------------------
//M5sen1_Read後の処理：得られたデータの表示など行う
//--------------------------------------------------
ble.onRead = function (data, uuid){
	let i;
	let value = "";
	let data1;
	
	var data_display = new Array('data_box0','data_box1','data_box2','data_box3','data_box4','data_box5','data_box6');
	
	startflag1 = 0;
	//フォーマットに従って値を取得
	for(i=0;i< data.byteLength;i++){
		value = value + String.fromCharCode(data.getInt8(i));
	}
	console.log(value);
	console.log("Sen1-"+cyc1);
	
	//数値化
	let array_atai =value.split(',');
	cyc1=Number(array_atai[0]);
	
	for(i=1;i<=100;i++){
		data1=Number(array_atai[i])/4095;
		data1=data1*5000;
		data1=Math.round(data1);
		array1[i-1][cyc1] = Number(data1);
	}
	
	if(cyc1==2){
		startflag1 = 1;
	}
	
	//document.getElementById('uuid_name').innerHTML = uuid;
	//document.getElementById('status').innerHTML = "read data"
	
	//グラフへ反映
	//ble_data.append(new Date().getTime(), value);
	
}

//--------------------------------------------------
//M5sen2_Read後の処理：得られたデータの表示など行う
//--------------------------------------------------
ble3.onRead = function (data, uuid){
	let i;
	let t=0;
	let value = "";
	let data1;
	
	var data_display = new Array('data_box0','data_box1','data_box2','data_box3','data_box4','data_box5','data_box6');
	
	startflag2 = 0;
	//フォーマットに従って値を取得
	for(i=0;i< data.byteLength;i++){
		value = value + String.fromCharCode(data.getInt8(i));
	}
	console.log(value);
	console.log("Sen2-"+cyc2);
	
	//数値化
	let array_atai =value.split(',');
	cyc2=Number(array_atai[0]);
	
	for(i=1;i<=100;i++){
		data1=Number(array_atai[i])/4095;
		data1=data1*5000;
		data1=Math.round(data1);
		array1[i-1][cyc2] = Number(data1);
	}
	
	if(cyc2==5){
		startflag2 = 1;
	}
	
	
	//document.getElementById('uuid_name').innerHTML = uuid;
	//document.getElementById('status').innerHTML = "read data"
	
	//グラフへ反映
	//ble_data.append(new Date().getTime(), value);
}




//--------------------------------------------------
//M5-1 Write後の処理
//--------------------------------------------------
ble2.onWrite = function(uuid){
  //document.getElementById('uuid_name').innerHTML = uuid;
  //document.getElementById('status').innerHTML = "written data"
}

//--------------------------------------------------
//M5-2 Write後の処理
//--------------------------------------------------
ble4.onWrite = function(uuid){
  //document.getElementById('uuid_name').innerHTML = uuid;
  //document.getElementById('status').innerHTML = "written data"
}




//--------------------------------------------------
//Start Notify後の処理
//--------------------------------------------------
ble.onStartNotify = function(uuid){
  console.log('> Start Notify!');

  //document.getElementById('uuid_name').innerHTML = uuid;
  //document.getElementById('status').innerHTML = "started Notify";
}


//--------------------------------------------------
//Stop Notify後の処理
//--------------------------------------------------
ble.onStopNotify = function(uuid){
  console.log('> Stop Notify!');

  //document.getElementById('uuid_name').innerHTML = uuid;
  //document.getElementById('status').innerHTML = "stopped Notify";
}


//-------------------------------------------------
//ボタンが押された時のイベント登録
//--------------------------------------------------
document.getElementById('startNotifications').addEventListener('click', function() {
      ble.startNotify('UUID1');
});

document.getElementById('stopNotifications').addEventListener('click', function() {
      ble.stopNotify('UUID1');
});
document.getElementById('startNotifications2').addEventListener('click', function() {
      ble3.startNotify('UUID1');
});

document.getElementById('stopNotifications2').addEventListener('click', function() {
      ble3.stopNotify('UUID1');
});

/*
document.getElementById('write').addEventListener('click', function() {
  //フォーマットに従って値を変換
  const textEncoder = new TextEncoder();
  const text_data = document.getElementById('write_value').value;
  const text_data_encoded = textEncoder.encode(text_data + '\n');

  //write
  ble2.write('UUID1', text_data_encoded);
});
*/


async function main() {
	while(true){
	    await wait(1); //
	    Create_grapf();
	}
}



const wait = (ms) => {
  return new Promise((resolve, reject) => {
    setTimeout(resolve, ms);
  });
};







function Create_grapf() {
	let screen_w = 600;
	let screen_h = 400;
	let Max_val = 5000;
	let Min_val = 0;
	let x1;
	let x2;
	let y1;
	let y2;
	
	let i=0;
	let ii=0;
	
	var plot_color = new Array('red', 'blue', 'yellow' ,'green','purple','pink','navy','teal','lime','aqua','fuchsia','maroon','gray','silver','skyblue');
	var Yokojiku = new Array('0.0','0.5','1.0','1.5','2.0','2.5','3.0','3.5','4.0');
	
	
	if(startflag1==1 &&  startflag2==1){
		
		let display_text="<svg xmlns='http://www.w3.org/2000/svg' version='1.1' height='" + screen_h + "' width='" + screen_w + "' viewBox='-50 -20 700 520' class='SvgFrame'>";
		
		//外枠
		display_text = display_text + "<rect x='0' y1='0' width='"+screen_w+"' height='"+screen_h+"' fill='white'  style='stroke:gray;stroke-width:1' />"
		
		//横目盛り線
		for(i=1;i<=9;i++){
			display_text = display_text + "<line x1='0' y1='" + screen_h/10*i + "' x2='" +  screen_w + "' y2='" + screen_h/10*i + "' style='stroke:gray;stroke-width:1' />";
		}
	
		//縦目盛り線
		for(i=1;i<=8;i++){
			display_text = display_text + "<line x1='" + screen_w/8*i + "' y1='0' x2='" + (screen_w/8*i) + "' y2='" + screen_h + "' style='stroke:gray;stroke-width:1' />";
		}
	
		//横目盛り
		for(i=0;i<=8;i++){	
			display_text = display_text + "<text fill='#448aff' font-family='Script' font-weight='bold'  x='" + screen_w/8*i + "' y='"+(screen_h+30)+"' font-size='20' text-anchor='middle' stroke-width='1'>"+Yokojiku[i]+"</text>"
		}
		
		//縦目盛り
		for(i=0;i<=10;i++){
	        display_text = display_text + "<text  fill='#448aff' font-family='Script' font-weight='bold'  x='-5' y='"+ (screen_h/10*i+10) +"' font-size='20' text-anchor='end' stroke-width='1'>"+(Max_val-(Max_val-Min_val)/10*i)/1000+"</text>"
	    }
	    
		
		//##########　X軸のタイトル表示　##########
		display_text = display_text + "<text  fill='#448aff' fill='#448aff' font-family='Comic Sans MS' font-weight='bold'  x='"+screen_w/10*5+"' y='"+(screen_h+70)+"' font-size='25' text-anchor='middle' stroke-width='1'>時間（秒）</text>"
		
	
		//##########　Y軸のタイトル表示　##########
		display_text = display_text + "<text  fill='#448aff' font-family='Script' font-weight='bold'  x='"+(-1*screen_h/2)+"' y='-65' font-size='25' text-anchor='middle' stroke-width='1' transform='rotate(-90,0,0)'>Output V(V)</text>"
		
		
		for(ii=0;ii<6;ii++){
		    x1 = 0;
		    
		    for(i=0;i<=98;i++){
		    	x2=0;
		        x2 = x1 + screen_w/100;
		        y1 = array1[i][ii]
		        y1 -= Min_val;
		        y1 *= screen_h;
		        y1 /= (Max_val - Min_val);
		        if(y1<0) y1=0;
		        if(y1>screen_h) y1=screen_h;
		        
		        y1 = screen_h - y1;
		        
		        y2 =  array1[(i+1)][ii];
		        y2 -= Min_val;
		        y2 *= screen_h;
		        y2 /= (Max_val - Min_val);
		        if(y2<0) y2=0;
		        if(y2>screen_h) y2=screen_h;
		        
		        y2 = screen_h - y2;
		        display_text = display_text + "<line x1='" + x1 + "' y1='" + y1 + "' x2='" + x2 + "' y2='" + y2 + "' style='stroke:"+ plot_color[ii] +";stroke-width:2' />";
		        
		        x1 += screen_w / 100
		        
		    }
	    }
	
	    
	    display_text += "</svg>"
	    document.getElementById("svg").innerHTML =  display_text;
	    
	    startflag1=0;
	    startflag2=0;
	}

}

</script>
</body>
</html>
