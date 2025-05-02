<!DOCTYPE html>
<html>
<head>
  <title>แผนที่พื้นที่ดำเนินการ</title>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
  <style>
    #map { height: 600px; width: 100%; }
  </style>
</head>
<body>

<h2>แผนที่พื้นที่ดำเนินการ</h2>
<div id="map"></div>

<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
<script>
  // เริ่มแผนที่
  var map = L.map('map').setView([15.8700, 100.9925], 6); // จุดกลางประเทศไทย

  // พื้นหลังแผนที่
  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '© OpenStreetMap contributors'
  }).addTo(map);

  // ข้อมูลตำแหน่ง
  const locations = [
    { name: "กรุงเทพฯ", lat: 13.7563, lng: 100.5018 },
    { name: "เชียงใหม่", lat: 18.7883, lng: 98.9853 },
    { name: "ขอนแก่น", lat: 16.4419, lng: 102.8350 }
  ];

  // วนลูปสร้าง marker
  locations.forEach(loc => {
    L.marker([loc.lat, loc.lng])
      .addTo(map)
      .bindPopup(`<b>${loc.name}</b>`);
  });
</script>

</body>
</html>
