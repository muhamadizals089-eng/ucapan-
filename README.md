<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<title>For You 💌</title>

<style>
body {
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(135deg, #1a2a33, #3a6073);
    overflow-x: hidden;
    color: white;
}

/* 💌 halaman awal */
.overlay {
    position: fixed;
    width: 100%;
    height: 100%;
    background: #0f2027;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    z-index: 10;
}

.btn {
    padding: 15px 25px;
    border: none;
    border-radius: 15px;
    background: #ff4d6d;
    color: white;
    font-size: 16px;
    cursor: pointer;
    box-shadow: 0 0 15px rgba(255,77,109,0.6);
}

/* 📩 card */
.card {
    display: none;
    margin: 40px auto;
    background: rgba(255,255,255,0.08);
    padding: 30px;
    border-radius: 20px;
    max-width: 600px;
    backdrop-filter: blur(10px);
    box-shadow: 0 0 30px rgba(0,0,0,0.4);
}

h1 {
    text-align: center;
    color: #FFD700;
}

#text {
    margin-top: 20px;
    line-height: 1.7;
    white-space: pre-line;
    font-size: 15px;
}

.footer {
    margin-top: 20px;
    text-align: right;
    color: #ffccd5;
}

/* ❤️ love jatuh */
.heart {
    position: fixed;
    top: -10px;
    color: #ff4d6d;
    font-size: 18px;
    animation: fall linear infinite;
}

@keyframes fall {
    to {
        transform: translateY(100vh);
        opacity: 0;
    }
}
</style>
</head>

<body>

<!-- 💌 Tampilan awal -->
<div class="overlay" id="overlay">
    <h2>💌 Ada pesan buat kamu</h2>
    <button class="btn" onclick="start()">Buka Pesan ❤️</button>
</div>

<!-- 📩 Isi pesan -->
<div class="card" id="card">
    <h1>🌙 Happy Eid Mubarak 🤍</h1>
    <div id="text"></div>
    <div class="footer">
        dari Fahrizal buat kamuu my kaylaa 🤍
    </div>
</div>

<script>
// Teks dibagi biar HP nggak nge-lag
const messageParts = [
`happy eid mubarak my favorite person 🤍🌙

di hari yang penuh maaf ini, akuu datang bukan cuma untuk minta maaf tapi juga buat minta maaf banget IHIHIHI
maafin akuu buat semua hal yang mungkin pernah nyakitin kamuu, buat sikap akuu yang egois, nyebelin, bikin kamuu sakit hati, dan sikap akuu yang kadang belum dewasa, untuk semua kata yang pernah ninggalin luka buat kamuu, dan maaf juga kalau selama ini akuu belum bisa bener-bener ngertiin kamuu seperti yang kamuu butuhin.

akuu sadar, nggak semua yang kita jalanin kemarin itu mudah, dan mungkin emang kita butuh waktu untuk sama-sama belajar.`,

`tapi sejauh apa pun kita sekarang, ada satu hal yang gak bakal berubah dari akuu yaitu cara akuu mandang kamuu masih sama. kamuu tetap jadi seseorang yang pernah akuu perjuangin dengan tulus, yang pernah jadi tempat paling nyaman, dan yang sampai sekarang masih punya ruang di hati akuu.

akuu nggak akan maksa waktu, nggak juga maksa keadaan. akuu cuma percaya, kalau sesuatu memang ditakdirkan untuk kembali, dia akan menemukan jalannya sendiri. dan kalau pun suatu hari nanti kita dipertemukan lagi, akuu harap itu bukan lagi versi kita yang dulu tapi versi kita yang lebih kuat, lebih tenang, dan lebih siap untuk saling menjaga.`,

`kalau sekarang kita harus berjalan sendiri dulu, nggak apa-apa. akuu tetap doain kamuu semoga bahagia, semoga hati kamuu tenang, dan semoga semua hal baik selalu dateng ke hidup kamuu.

selamat hari raya idul fitri, mohon maaf lahir dan batin 🤍✨
dan di antara semua doa yang akuu panjatkan hari ini ada satu nama yang masih akuu sebut dengan pelan.

akuu nggak tahu kapan atau gimana caranya, tapi akuu masih nyimpen harapan kecil semoga suatu hari nanti kita bisa kembali, bukan sekadar mengulang, tapi memperbaiki jadi kita yang lebih baik dari sebelumnya.`
];

let partIndex = 0;
let charIndex
