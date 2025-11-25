<?php

use FlashWalker\Weatherapp\WeatherService;
use Symfony\Component\Dotenv\Dotenv;

require_once __DIR__ . '/vendor/autoload.php';

$dotenv = new Dotenv();
$dotenv->load(__DIR__.'/.env');


if($argc < 2) {
    echo "You need to specify the city";
    exit;
}else {

    $weatherService = new WeatherService();
    
    $city = $argv['1'];
    
    echo "Getting weather for $city ... \n";
    
    try {
        $weather = $weatherService->getWeather($city);
    
        // var_dump($weather);
    
        echo "\n";
    
        echo "City: " . $weather['city'] . "\n";
        echo "Temperature: " . $weather['temperature'] . "°C\n";
        echo "Description: " . $weather['description'] . "\n";
        echo "Humidity: " . $weather['humidity'] . "%\n\n";
    
    } catch (\Throwable $th) {
        echo $th->getMessage();
    }
}
