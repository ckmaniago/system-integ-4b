<template>
<div class="weather-container">
<!-- Screen 1: Welcome -->
<div class="screen active" id="screen1">
<div class="icon-wrapper">
<div class="sun-cloud">
<div class="sun"></div>
<div class="cloud"></div>
<div class="rain">
<span></span><span></span><span></span>
</div>
</div>
</div>
<h1>Weather Forecasts</h1>
<button class="start-btn">Get Start</button>
</div>

<!-- Screen 2: 7-Day Forecast -->
<div class="screen" id="screen2">
<div class="location-info">
<h2>Gilgit Baltistan</h2>
<p class="temp-range">Max:66.2° &nbsp; Min:44°</p>
</div>

<h3 class="section-title">7-Days Forecasts</h3>
<div class="forecast-row">
<div class="day-card">
<p>20°C</p>
<div class="weather-icon">☀️</div>
<span>Mon</span>
</div>
<div class="day-card">
<p>20°C</p>
<div class="weather-icon">⛅</div>
<span>Tue</span>
</div>
<div class="day-card">
<p>20°C</p>
<div class="weather-icon">☁️</div>
<span>Wed</span>
</div>
<div class="day-card">
<p>20°C</p>
<div class="weather-icon">⛈️</div>
<span>Thu</span>
</div>
</div>

<div class="card air-quality-card">
<h4>Air Quality</h4>
<p class="aq-status">3- Low Health Risk</p>
<div class="see-more">See More <span>›</span></div>
</div>

<div class="info-grid">
<div class="info-card">
<h4>Air Quality</h4>
<p>5:23 AM</p>
<span>Sunset 7:23 PM</span>
</div>
<div class="info-card">
<h4>UV Index</h4>
<p>4</p>
<span>Moderate</span>
</div>
</div>
</div>

<!-- Screen 3: Today's Detail -->
<div class="screen" id="screen3">
<div class="main-weather-icon">
<div class="sun-big"></div>
<div class="cloud-big"></div>
<div class="rain-big">
<span></span><span></span><span></span>
</div>
</div>

<div class="main-temp">19°C</div>
<div class="location-info">
<h2>Gilgit Baltistan</h2>
<p class="temp-range">Max:66.2° &nbsp; Min:44°</p>
</div>

<div class="today-table">
<div class="table-header">
<span>Today</span>
<span>July, 11</span>
</div>
<div class="table-row">
<div class="col">
<p>20°C</p><span>☀️</span><small>13.31</small>
</div>
<div class="col">
<p>14°C</p><span>⛅</span><small>23.32</small>
</div>
<div class="col">
<p>09°C</p><span>☁️</span><small>32.31</small>
</div>
<div class="col">
<p>10°C</p><span>🌧️</span><small>13.32</small>
</div>
<div class="col">
<p>16°C</p><span>⛈️</span><small>16.31</small>
</div>
</div>
</div>
</div>
</div>
</template>

<style scoped>
.weather-container {
min-height: 100vh;
background: linear-gradient(135deg, #2a1b50 0%, #4b2e91 100%);
padding: 2rem;
font-family: 'Segoe UI', sans-serif;
color: white;
}

.screen {
display: none;
max-width: 380px;
margin: 0 auto;
padding: 2rem 1.5rem;
}

.screen.active {
display: block;
}

/* Screen 1 Styles */
.icon-wrapper {
display: flex;
justify-content: center;
margin: 3rem 0;
}

.sun-cloud {
position: relative;
width: 160px;
height: 140px;
}

.sun {
position: absolute;
top: 10px;
right: 10px;
width: 80px;
height: 80px;
background: #ffd300;
border-radius: 50%;
box-shadow: 0 0 30px #ffd300;
}

.sun::before, .sun-big::before {
content: '';
position: absolute;
width: 100%;
height: 100%;
background: inherit;
border-radius: 50%;
}

.cloud {
position: absolute;
bottom: 30px;
left: 20px;
width: 100px;
height: 50px;
background: #fff;
border-radius: 50px;
}

.cloud::before, .cloud::after {
content: '';
position: absolute;
background: #fff;
border-radius: 50%;
}

.cloud::before {
width: 50px;
height: 50px;
top: -25px;
left: 10px;
}

.cloud::after {
width: 35px;
height: 35px;
top: -15px;
right: 10px;
}

.rain {
position: absolute;
bottom: 0;
left: 40px;
display: flex;
gap: 12px;
}

.rain span {
width: 8px;
height: 14px;
background: #6ab7ff;
border-radius: 50%;
border-radius: 0 0 50% 50%;
}

.screen h1 {
text-align: center;
font-size: 1.8rem;
margin-bottom: 3rem;
}

.start-btn {
display: block;
width: 100%;
padding: 1rem;
background: #ffd300;
border: none;
border-radius: 12px;
font-size: 1.1rem;
font-weight: 600;
color: #2a1b50;
cursor: pointer;
}

/* Shared Styles */
.location-info {
text-align: center;
margin-bottom: 1.5rem;
}

.location-info h2 {
font-size: 1.3rem;
margin-bottom: 0.3rem;
}

.temp-range {
opacity: 0.7;
font-size: 0.95rem;
}

.section-title {
font-size: 1.1rem;
margin-bottom: 1rem;
}

/* 7-Day Forecast */
.forecast-row {
display: flex;
justify-content: space-between;
gap: 8px;
margin-bottom: 1.5rem;
}

.day-card {
background: rgba(255,255,255,0.1);
border-radius: 12px;
padding: 1rem 0.5rem;
text-align: center;
flex: 1;
}

.day-card p {
font-weight: 600;
margin-bottom: 0.5rem;
}

.weather-icon {
font-size: 1.4rem;
margin-bottom: 0.3rem;
}

.day-card span {
font-size: 0.8rem;
opacity: 0.8;
}

.card {
background: rgba(79, 59, 167, 0.4);
border-radius: 12px;
padding: 1rem;
margin-bottom: 1rem;
}

.air-quality-card h4 {
font-size: 0.9rem;
opacity: 0.7;
margin-bottom: 0.5rem;
}

.aq-status {
font-size: 1.1rem;
font-weight: 600;
margin-bottom: 0.5rem;
}

.see-more {
text-align: right;
font-size: 0.85rem;
opacity: 0.6;
}

.info-grid {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 12px;
}

.info-card {
background: rgba(79, 59, 167, 0.4);
border-radius: 12px;
padding: 1rem;
}

.info-card h4 {
font-size: 0.85rem;
opacity: 0.7;
margin-bottom: 0.5rem;
}

.info-card p {
font-size: 1rem;
font-weight: 600;
margin-bottom: 0.3rem;
}

.info-card span {
font-size: 0.8rem;
opacity: 0.6;
}

/* Screen 3 Styles */
.main-weather-icon {
display: flex;
justify-content: center;
margin: 2rem 0;
position: relative;
height: 140px;
}

.sun-big {
position: absolute;
top: 20px;
right: 60px;
width: 90px;
height: 90px;
background: #ffd300;
border-radius: 50%;
box-shadow: 0 0 30px #ffd300;
}

.cloud-big {
position: absolute;
bottom: 30px;
left: 80px;
width: 120px;
height: 60px;
background: #fff;
border-radius: 60px;
}

.cloud-big::before, .cloud-big::after {
content: '';
position: absolute;
background: #fff;
border-radius: 50%;
}

.cloud-big::before {
width: 60px;
height: 60px;
top: -30px;
left: 10px;
}

.cloud-big::after {
width: 40px;
height: 40px;
top: -15px;
right: 15px;
}

.rain-big {
position: absolute;
bottom: 10px;
left: 130px;
display: flex;
gap: 10px;
}

.rain-big span {
width: 10px;
height: 16px;
background: #6ab7ff;
border-radius: 0 0 50% 50%;
}

.main-temp {
text-align: center;
font-size: 2.5rem;
font-weight: 700;
margin-bottom: 0.5rem;
}

.today-table {
background: rgba(79, 59, 167, 0.4);
border-radius: 12px;
padding: 1rem;
margin-top: 1.5rem;
}

.table-header {
display: flex;
justify-content: space-between;
font-size: 0.9rem;
opacity: 0.7;
margin-bottom: 1rem;
}

.table-row {
display: flex;
justify-content: space-between;
text-align: center;
}

.table-row .col {
flex: 1;
}

.table-row p {
font-size: 0.9rem;
font-weight: 600;
margin-bottom: 0.3rem;
}

.table-row span {
font-size: 1rem;
display: block;
margin-bottom: 0.2rem;
}

.table-row small {
font-size: 0.7rem;
opacity: 0.6;
}
</style>