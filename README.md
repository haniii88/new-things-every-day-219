```javascript
function dailyLog219() {
  const weatherData = [
    { city: "Berlin", temperature: 18, humidity: 65 },
    { city: "Munich", temperature: 22, humidity: 55 },
    { city: "Hamburg", temperature: 15, humidity: 78 },
    { city: "Frankfurt", temperature: 25, humidity: 45 },
    { city: "Cologne", temperature: 20, humidity: 60 },
  ];

  const averageTemp =
    weatherData.reduce(
      (sum, city) => sum + city.temperature,
      0
    ) / weatherData.length;

  const hottest = weatherData.reduce((a, b) =>
    a.temperature > b.temperature ? a : b
  );

  const coldest = weatherData.reduce((a, b) =>
    a.temperature < b.temperature ? a : b
  );

  console.log("=== Weather Analysis Report ===");
  console.log(`Cities Analyzed: ${weatherData.length}`);
  console.log(`Average Temperature: ${averageTemp.toFixed(1)}°C`);
  console.log(`Hottest City: ${hottest.city}`);
  console.log(`Coldest City: ${coldest.city}`);

  console.log("\n=== City Details ===");

  weatherData.forEach(city => {
    const condition =
      city.temperature >= 25 ? "☀️ Hot" :
      city.temperature >= 18 ? "🌤️ Mild" : "🌧️ Cool";

    console.log(
      `${city.city}: ${city.temperature}°C, ` +
      `Humidity: ${city.humidity}% — ${condition}`
    );
  });

  console.log("\n🌍 Weather analysis completed!");
}

dailyLog219();
```
