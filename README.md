<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Game Matematika Kelas X</title>
    <style>
        /* CSS: Mengatur Tampilan agar Keren dan Rapi */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #1a1a2e;
            color: #ffffff;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .game-container {
            background-color: #16213e;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.5);
            width: 80%;
            max-width: 600px;
            text-align: center;
        }
        .opsi-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-top: 20px;
        }
        button {
            background-color: #0f3460;
            color: white;
            border: none;
            padding: 15px;
            font-size: 16px;
            border-radius: 8px;
            cursor: pointer;
            transition: 0.2s;
        }
        button:hover {
            background-color: #e94560;
        }
        #skor-display {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
            color: #4eed96;
        }
    </style>
</head>
<body>

    <div class="game-container">
        <h2>Game Matematika Kelas X</h2>
        <hr style="border-color: #e94560;">
        
        <p id="pertanyaan" style="font-size: 20px; margin: 30px 0;"></p>
        
        <div class="opsi-container">
            <button onclick="pilihJawaban(0)" id="opsi0">Pilihan A</button>
            <button onclick="pilihJawaban(1)" id="opsi1">Pilihan B</button>
            <button onclick="pilihJawaban(2)" id="opsi2">Pilihan C</button>
            <button onclick="pilihJawaban(3)" id="opsi3">Pilihan D</button>
        </div>

        <div id="skor-display">Skor: 0</div>
    </div>

    <script>
        // JAVASCRIPT: Otak dari Gamenya
        
        // 1. Bank Soal Matematika Kelas X
        const bankSoal = [
            {
                soal: "Jika x + y = 5 dan x - y = 1, berapakah nilai x?",
                pilihan: ["2", "3", "4", "1"],
                jawabanBenar: 1 
            },
            {
                soal: "Suku ke-5 dari barisan 2, 5, 8, 11, ... adalah?",
                pilihan: ["14", "15", "16", "17"],
                jawabanBenar: 0
            },
            {
                soal: "Jika diketahui x² + y³ = 17 dan 2x² - y³ = 10, maka nilai dari x² · y³ adalah...",
                pilihan: ["24", "89", "72", "38"],
                jawabanBenar: 2
            },
            {
                soal: "Diketahui persamaan x⁴ + y⁵ = 33. Jika nilai x = 2, maka nilai y yang memenuhi persamaan tersebut adalah...",
                pilihan: ["1", "2", "3", "4"],
                jawabanBenar: 0
            },
            {
                soal: "Jika x⁴ + y² = 25 dengan x dan y adalah bilangan real, maka nilai maksimum yang mungkin untuk variabel y adalah...",
                pilihan: ["25", "5", "24", "2"],
                jawabanBenar: 1
            },
            {
                soal: "Diketahui sistem persamaan: a³ + b⁴ = 40 dan 3a³ - 2b⁴ = 5. Nilai dari b⁴ - a³ adalah...",
                pilihan: ["58", "8", "11", "17"],
                jawabanBenar: 1
            },
            {
                soal: "Jika x⁴ + y⁷ = 19, maka nilai dari bentuk aljabar 3x⁴ + 3y⁷ - 15 adalah...",
                pilihan: ["32", "42", "57", "62"],
                jawabanBenar: 1
            },
            {
                soal: "Banyaknya pasangan bilangan bulat positif (x, y) yang memenuhi persamaan x³ + y² = 12 adalah...",
                pilihan: ["0", "1", "2", "3"],
                jawabanBenar: 1
            },
            {
                soal: "Jika x⁴ + y⁷ = 19 dan nilai x⁴ = 3, maka nilai dari ²log(y⁷ - 12) adalah...",
                pilihan: ["1", "2", "3", "4"],
                jawabanBenar: 1
            }
        ]; // <-- Tanda penutup array sudah dikembalikan ke sini

        let indeksSekarang = 0;
        let skor = 0;

        // 2. Fungsi untuk menampilkan soal ke layar HTML
        function tampilkanSoal() {
            if (indeksSekarang < bankSoal.length) {
                let soalAktif = bankSoal[indeksSekarang];
                document.getElementById("pertanyaan").innerText = soalAktif.soal;
                document.getElementById("opsi0").innerText = soalAktif.pilihan[0];
                document.getElementById("opsi1").innerText = soalAktif.pilihan[1];
                document.getElementById("opsi2").innerText = soalAktif.pilihan[2];
                document.getElementById("opsi3").innerText = soalAktif.pilihan[3];
            } else {
                document.getElementById("pertanyaan").innerText = "Permainan Selesai! Terima kasih sudah bermain.";
                document.querySelector(".opsi-container").style.display = "none";
            }
        }

        // 3. Fungsi untuk mengecek jawaban yang diklik pemain
        function pilihJawaban(indeksPilihan) {
            let soalAktif = bankSoal[indeksSekarang];
            
            if (indeksPilihan === soalAktif.jawabanBenar) {
                alert("Benar! 🎉");
                skor += 10;
                document.getElementById("skor-display").innerText = "Skor: " + skor;
            } else {
                alert("Salah! ❌");
            }

            // Lanjut ke soal berikutnya
            indeksSekarang++;
            tampilkanSoal();
        }

        // Jalankan fungsi pertama kali saat web dibuka
        tampilkanSoal();
    </script>
</body>
</html>
