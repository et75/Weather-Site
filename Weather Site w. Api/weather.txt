<?php
$zip = $_GET["zip"];
$url = "http://api.openweathermap.org/data/2.5/weather?zip=".$zip.","."us&units=imperial&appid=804159ae3bbde279e3bd6af8d1adb493";

$fp = fopen ($url , "r" ) or die ("unable to contact the $url");
$weatherinfo = "";
while ( $more = fread ($fp, 1000) ){
	$weatherinfo .= $more;
}
echo $weatherinfo;
?>