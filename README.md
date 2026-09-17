# Web-Mini-e-Commerce
Repository untuk Web Mini E Commerce
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mini E-Commerce</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            background-color: #f4f4f4;
            color: #333;
        }

        header {
            background-color: #222;
            color: white;
            padding: 20px;
            text-align: center;
        }

        header h1 {
            margin: 0;
        }

        .container {
            width: 90%;
            max-width: 1000px;
            margin: 30px auto;
        }

        .produk-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
        }

        .produk {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        .produk h3 {
            margin-bottom: 10px;
        }

        .harga {
            font-weight: bold;
            color: #e63946;
            margin-bottom: 15px;
        }

        button {
            background-color: #222;
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #444;
        }

        .keranjang {
            background-color: white;
            margin-top: 30px;
            padding: 20px;
            border-radius: 10px;
        }

        #total {
            font-size: 20px;
            font-weight: bold;
            margin-top: 15px;
        }
    </style>
</head>

<body>

    <header>
        <h1>🛒 Mini E-Commerce</h1>
        <p>Belanja mudah dan sederhana</p>
    </header>

    <div class="container">

        <h2>Daftar Produk</h2>

        <div class="produk-container">

            <div class="produk">
                <h3>Kaos</h3>
                <p class="harga">Rp50.000</p>
                <button onclick="tambahProduk(50000)">
                    Tambah ke Keranjang
                </button>
            </div>

            <div class="produk">
                <h3>Celana</h3>
                <p class="harga">Rp75.000</p>
                <button onclick="tambahProduk(75000)">
                    Tambah ke Keranjang
                </button>
            </div>

            <div class="produk">
                <h3>Sepatu</h3>
                <p class="harga">Rp150.000</p>
                <button onclick="tambahProduk(150000)">
                    Tambah ke Keranjang
                </button>
            </div>

            <div class="produk">
                <h3>Tas</h3>
                <p class="harga">Rp100.000</p>
                <button onclick="tambahProduk(100000)">
                    Tambah ke Keranjang
                </button>
            </div>

        </div>

        <div class="keranjang">
            <h2>🛍️ Keranjang</h2>

            <p>Jumlah produk: <span id="jumlah">0</span></p>

            <p id="total">
                Total: Rp0
            </p>

            <button onclick="checkout()">
                Checkout
            </button>
        </div>

    </div>

    <script>
        let jumlahProduk = 0;
        let totalHarga = 0;

        function tambahProduk(harga) {
            jumlahProduk++;
            totalHarga += harga;

            document.getElementById("jumlah").innerText = jumlahProduk;

            document.getElementById("total").innerText =
                "Total: Rp" + totalHarga.toLocaleString("id-ID");
        }

        function checkout() {
            if (jumlahProduk === 0) {
                alert("Keranjang masih kosong!");
            } else {
                alert(
                    "Checkout berhasil!\n" +
                    "Jumlah produk: " + jumlahProduk +
                    "\nTotal pembayaran: Rp" +
                    totalHarga.toLocaleString("id-ID")
                );
            }
        }
    </script>

</body>
</html>
