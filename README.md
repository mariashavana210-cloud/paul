<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes, viewport-fit=cover">
  <title>Maria · Keuangan Jajan</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: linear-gradient(145deg, #f9efe2 0%, #fdf3e5 100%);
      font-family: 'Segoe UI', 'Poppins', system-ui, -apple-system, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      margin: 0;
      padding: 1rem;
    }

    .app-container {
      max-width: 480px;
      width: 100%;
      background: rgba(255, 248, 240, 0.85);
      backdrop-filter: blur(20px);
      -webkit-backdrop-filter: blur(20px);
      background: #fffaf2;
      border-radius: 2.5rem;
      box-shadow: 0 30px 50px rgba(0, 0, 0, 0.08), 0 10px 20px rgba(150, 100, 50, 0.1);
      padding: 1.8rem 1.5rem 2.2rem;
      border: 1px solid rgba(230, 190, 130, 0.3);
      transition: all 0.2s ease;
    }

    .header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 2rem;
    }

    .logo-area {
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .app-title {
      font-size: 2.2rem;
      font-weight: 700;
      letter-spacing: -0.5px;
      background: linear-gradient(135deg, #c0843c, #b56532);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      cursor: pointer;
      transition: transform 0.2s ease, filter 0.2s;
      text-shadow: 2px 2px 8px rgba(180, 120, 60, 0.15);
      line-height: 1.1;
    }

    .app-title:active {
      transform: scale(0.96);
      filter: brightness(1.2);
    }

    .saldo-card {
      background: #f3e5d5;
      border-radius: 2rem;
      padding: 1.2rem 1.5rem;
      background: linear-gradient(105deg, #f7e9d7, #fae9d0);
      box-shadow: inset 0 1px 4px rgba(255, 255, 255, 0.8), 0 8px 18px rgba(160, 110, 50, 0.15);
      margin-bottom: 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border: 1px solid #e7c9a0;
    }

    .saldo-label {
      font-size: 0.9rem;
      font-weight: 500;
      color: #7b5e3b;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }

    .saldo-amount {
      font-size: 2rem;
      font-weight: 700;
      color: #4e3b28;
      display: flex;
      align-items: baseline;
      gap: 0.2rem;
    }

    .saldo-amount span {
      font-size: 1rem;
      font-weight: 600;
      color: #8b6f4c;
    }

    .menu-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 1rem;
      margin-bottom: 2rem;
    }

    .menu-item {
      background: white;
      border-radius: 1.5rem;
      padding: 1.2rem 0.8rem;
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      background: #fffdf7;
      box-shadow: 0 10px 18px rgba(140, 90, 30, 0.08);
      border: 1px solid #eddcc9;
      transition: all 0.2s ease;
      cursor: pointer;
      user-select: none;
    }

    .menu-item:active {
      transform: translateY(2px);
      box-shadow: 0 5px 12px rgba(120, 70, 20, 0.2);
      background: #fff7ec;
    }

    .emoji-food {
      font-size: 2.6rem;
      margin-bottom: 0.4rem;
      filter: drop-shadow(0 6px 6px rgba(0,0,0,0.1));
    }

    .food-name {
      font-weight: 700;
      font-size: 1rem;
      color: #5a3f28;
      margin-bottom: 0.2rem;
    }

    .food-price {
      font-size: 0.85rem;
      font-weight: 600;
      color: #b37b44;
      background: #f9efe2;
      padding: 0.25rem 1rem;
      border-radius: 2rem;
      margin-top: 0.3rem;
    }

    .input-section {
      background: #fffaf3;
      border-radius: 1.8rem;
      padding: 1.2rem 1.2rem 1rem;
      margin: 1.5rem 0 1.2rem;
      border: 1px solid #e7d3bb;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 0.8rem;
    }

    .custom-input {
      flex: 2;
      min-width: 140px;
      display: flex;
      align-items: center;
      background: white;
      border-radius: 2.5rem;
      padding: 0.2rem 0.2rem 0.2rem 1.2rem;
      border: 1px solid #ddc3a5;
      background: #fffbf5;
    }

    .custom-input span {
      font-weight: 600;
      color: #b48b54;
      margin-right: 0.3rem;
    }

    .custom-input input {
      border: none;
      background: transparent;
      padding: 0.8rem 0.4rem;
      font-size: 1rem;
      font-weight: 500;
      width: 100%;
      outline: none;
      color: #4b3621;
    }

    .custom-input input::placeholder {
      color: #ccb699;
      font-weight: 400;
    }

    .add-btn {
      background: #dba46a;
      border: none;
      background: linear-gradient(135deg, #cf9f6b, #bb7e4a);
      color: white;
      font-weight: 700;
      padding: 0.9rem 1.3rem;
      border-radius: 2.5rem;
      font-size: 0.95rem;
      letter-spacing: 0.4px;
      cursor: pointer;
      box-shadow: 0 8px 15px rgba(180, 110, 30, 0.3);
      transition: 0.2s ease;
      display: flex;
      align-items: center;
      gap: 0.2rem;
      border: 1px solid #c29252;
      white-space: nowrap;
    }

    .add-btn:active {
      background: linear-gradient(135deg, #b5804a, #9f6a3a);
      box-shadow: 0 4px 10px rgba(140, 80, 20, 0.4);
      transform: scale(0.96);
    }

    .reset-area {
      display: flex;
      justify-content: flex-end;
      margin-top: 0.5rem;
    }

    .reset-btn {
      background: transparent;
      border: 1px solid #e1c6a8;
      color: #9b7a5a;
      font-weight: 600;
      padding: 0.55rem 1.4rem;
      border-radius: 2rem;
      font-size: 0.85rem;
      cursor: pointer;
      background: #fff6ed;
      transition: 0.2s;
      display: flex;
      align-items: center;
      gap: 0.3rem;
    }

    .reset-btn:active {
      background: #fae3cd;
      color: #684e32;
      border-color: #c49a6c;
    }

    .riwayat-title {
      font-weight: 700;
      color: #6b4f32;
      margin: 1.2rem 0 0.7rem;
      font-size: 1rem;
      display: flex;
      align-items: center;
      gap: 0.4rem;
    }

    .history-list {
      list-style: none;
      max-height: 160px;
      overflow-y: auto;
      background: #fffdf7;
      border-radius: 1.5rem;
      padding: 0.5rem 0.8rem;
      border: 1px solid #f0ddc4;
      font-size: 0.9rem;
      color: #4f3a26;
    }

    .history-list li {
      padding: 0.5rem 0.3rem;
      border-bottom: 1px dashed #ead3b8;
      display: flex;
      justify-content: space-between;
      font-weight: 500;
    }

    .history-list li:last-child {
      border-bottom: none;
    }

    .empty-history {
      color: #b9a083;
      text-align: center;
      padding: 1rem;
      font-style: italic;
    }

    .footer-note {
      text-align: center;
      margin-top: 1rem;
      color: #bfa68b;
      font-size: 0.7rem;
      font-weight: 500;
      letter-spacing: 0.3px;
    }

    @media (max-width: 400px) {
      .app-container {
        padding: 1.4rem 1rem;
      }
      .menu-grid {
        gap: 0.7rem;
      }
    }
  </style>
</head>
<body>
<div class="app-container">
  <!-- Header dengan nama aplikasi yang bisa diklik -->
  <div class="header">
    <div class="logo-area">
      <span style="font-size: 2rem; margin-right: 0.2rem;">🥘</span>
      <!-- Nama aplikasi "maria" dapat diklik -->
      <h1 class="app-title" id="mariaClickable">maria</h1>
    </div>
    <div style="font-size: 1.8rem; opacity: 0.7;">🍽️</div>
  </div>

  <!-- Saldo -->
  <div class="saldo-card">
    <div>
      <div class="saldo-label">💰 Saldo Jajan</div>
      <div class="saldo-amount" id="saldoDisplay">150000<span>IDR</span></div>
    </div>
    <div style="font-size: 2.2rem;">🍜</div>
  </div>

  <!-- Menu jajan -->
  <div class="menu-grid">
    <!-- Nasi Goreng -->
    <div class="menu-item" data-food="Nasi Goreng" data-price="18000">
      <span class="emoji-food">🍛</span>
      <span class="food-name">Nasi Goreng</span>
      <span class="food-price">Rp18.000</span>
    </div>
    <!-- Martabak -->
    <div class="menu-item" data-food="Martabak" data-price="22000">
      <span class="emoji-food">🫓</span>
      <span class="food-name">Martabak</span>
      <span class="food-price">Rp22.000</span>
    </div>
    <!-- Nasi Padang -->
    <div class="menu-item" data-food="Nasi Padang" data-price="25000">
      <span class="emoji-food">🍱</span>
      <span class="food-name">Nasi Padang</span>
      <span class="food-price">Rp25.000</span>
    </div>
    <!-- Mie Goreng -->
    <div class="menu-item" data-food="Mie Goreng" data-price="15000">
      <span class="emoji-food">🍝</span>
      <span class="food-name">Mie Goreng</span>
      <span class="food-price">Rp15.000</span>
    </div>
  </div>

  <!-- Input custom nominal & tambah manual -->
  <div class="input-section">
    <div class="custom-input">
      <span>Rp</span>
      <input type="number" id="customNominalInput" placeholder="Nominal" min="0" value="">
    </div>
    <button class="add-btn" id="addCustomBtn">➕ Tambah</button>
  </div>

  <!-- Tombol reset & info -->
  <div class="reset-area">
    <button class="reset-btn" id="resetSaldoBtn">
      <span>↺</span> Reset Saldo
    </button>
  </div>

  <!-- Riwayat jajan -->
  <div class="riwayat-title">
    <span>📋 Riwayat Jajan</span>
    <span style="font-size:0.8rem; margin-left:auto; color:#b3926c;" id="totalPengeluaranKecil"></span>
  </div>
  <ul class="history-list" id="historyContainer">
    <li class="empty-history">Belum ada jajan hari ini</li>
  </ul>
  <div class="footer-note">
    klik <strong>maria</strong> untuk info · ketuk menu langsung kurangi saldo
  </div>
</div>

<script>
  (function() {
    // --- STATE ---
    let saldo = 150000;           // saldo awal
    const history = [];           // menyimpan array of { foodName, price, timestamp }

    // DOM elements
    const saldoDisplay = document.getElementById('saldoDisplay');
    const historyContainer = document.getElementById('historyContainer');
    const totalPengeluaranKecil = document.getElementById('totalPengeluaranKecil');
    const customNominalInput = document.getElementById('customNominalInput');
    const addCustomBtn = document.getElementById('addCustomBtn');
    const resetSaldoBtn = document.getElementById('resetSaldoBtn');
    const mariaTitle = document.getElementById('mariaClickable');

    // Semua menu item (nasi goreng, martabak, nasi padang, mie goreng)
    const menuItems = document.querySelectorAll('.menu-item');

    // --- FUNCTIONS ---

    // Format currency
    function formatRupiah(angka) {
      return angka.toLocaleString('id-ID');
    }

    // Update tampilan saldo
    function updateSaldoDisplay() {
      // Pastikan saldo tidak negatif (jika sengaja dipotong tapi bisa saja dicegah)
      if (saldo < 0) saldo = 0;
      saldoDisplay.innerHTML = `${formatRupiah(saldo)}<span>IDR</span>`;
    }

    // Hitung total pengeluaran dari history
    function getTotalPengeluaran() {
      return history.reduce((total, item) => total + item.price, 0);
    }

    // Render ulang riwayat dan update label kecil
    function renderHistory() {
      historyContainer.innerHTML = '';
      
      if (history.length === 0) {
        historyContainer.innerHTML = '<li class="empty-history">Belum ada jajan hari ini</li>';
        totalPengeluaranKecil.textContent = '';
        return;
      }

      // Tampilkan dari terbaru ke lama (opsional, bisa oldest first; tapi user friendly terbaru di atas)
      const reversed = [...history].reverse();
      reversed.forEach(item => {
        const li = document.createElement('li');
        const timeStr = new Date(item.timestamp).toLocaleTimeString('id-ID', { hour: '2-digit', minute: '2-digit' });
        li.innerHTML = `<span>🍴 ${item.foodName}</span> <span style="color:#b08968; font-weight:600;">-Rp${formatRupiah(item.price)} <span style="font-size:0.7rem; color:#b6a086;">${timeStr}</span></span>`;
        historyContainer.appendChild(li);
      });

      const total = getTotalPengeluaran();
      totalPengeluaranKecil.textContent = `Total: Rp${formatRupiah(total)}`;
    }

    // Fungsi utama mengurangi saldo (digunakan oleh menu dan custom)
    function kurangiSaldo(foodName, price) {
      // Validasi harga
      const harga = parseInt(price, 10);
      if (isNaN(harga) || harga <= 0) {
        alert('Masukkan nominal yang valid (lebih dari 0).');
        return false;
      }

      if (saldo < harga) {
        alert(`❌ Saldo tidak cukup! Kurang Rp${formatRupiah(harga - saldo)}.`);
        return false;
      }

      // Kurangi saldo
      saldo -= harga;
      
      // Catat ke history
      const newRecord = {
        foodName: foodName,
        price: harga,
        timestamp: new Date().toISOString()
      };
      history.push(newRecord);

      // Update UI
      updateSaldoDisplay();
      renderHistory();
      
      // Reset input custom jika ada
      if (customNominalInput) {
        customNominalInput.value = '';
      }
      return true;
    }

    // Handler untuk klik menu (nasi goreng, martabak, dll)
    function handleMenuClick(event) {
      const menuDiv = event.currentTarget;
      const food = menuDiv.getAttribute('data-food');
      const price = menuDiv.getAttribute('data-price');
      
      if (!food || !price) return;
      
      // Konfirmasi ringan (opsional, bisa langsung)
      const konfirmasi = confirm(`Beli ${food} seharga Rp${formatRupiah(parseInt(price))}?`);
      if (konfirmasi) {
        kurangiSaldo(food, parseInt(price, 10));
      }
    }

    // Tambah custom nominal (user masukkan nominal sendiri)
    function tambahCustomNominal() {
      const rawValue = customNominalInput.value.trim();
      if (rawValue === '') {
        alert('Masukkan nominal terlebih dahulu.');
        return;
      }
      const nominal = parseInt(rawValue, 10);
      if (isNaN(nominal) || nominal <= 0) {
        alert('Nominal harus angka positif.');
        return;
      }
      
      // Nama makanan custom
      const foodName = `Jajan (Rp${formatRupiah(nominal)})`;
      kurangiSaldo(foodName, nominal);
    }

    // Reset saldo ke nilai awal (150000) dan hapus history
    function resetSaldoDanHistory() {
      const konfirmasi = confirm('Reset saldo ke Rp150.000 dan hapus semua riwayat jajan?');
      if (!konfirmasi) return;
      
      saldo = 150000;
      // Kosongkan history array
      history.length = 0;
      
      updateSaldoDisplay();
      renderHistory();
      if (customNominalInput) customNominalInput.value = '';
    }

    // Fungsi ketika nama "maria" diklik
    function onMariaClick() {
      alert('✨ Maria · Catatan Keuangan Jajan ✨\n\n🍲 Nasi Goreng · Martabak · Nasi Padang · Mie Goreng\nKelola jajanmu dengan bijak!');
    }

    // --- EVENT LISTENERS ---
    
    // Pasang event di setiap menu item
    menuItems.forEach(item => {
      item.addEventListener('click', handleMenuClick);
    });

    // Tombol tambah custom
    addCustomBtn.addEventListener('click', tambahCustomNominal);

    // Enter pada input custom juga trigger tambah
    customNominalInput.addEventListener('keypress', (e) => {
      if (e.key === 'Enter') {
        e.preventDefault();
        tambahCustomNominal();
      }
    });

    // Reset saldo
    resetSaldoBtn.addEventListener('click', resetSaldoDanHistory);

    // Klik pada judul "maria"
    mariaTitle.addEventListener('click', onMariaClick);

    // Inisialisasi tampilan
    updateSaldoDisplay();
    renderHistory();
    
    // Pastikan input custom bersih
    customNominalInput.value = '';
  })();
</script>
</body>
</html># paul
