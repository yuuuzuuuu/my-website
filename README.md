<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Catatan Uang Jajan</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script defer>
    document.addEventListener("DOMContentLoaded", () => {
      const tabs = document.querySelectorAll(".tab");
      const pages = document.querySelectorAll(".page");
      tabs.forEach((tab, i) => {
        tab.addEventListener("click", () => {
          pages.forEach(p => p.classList.add("hidden"));
          tabs.forEach(t => t.classList.remove("text-primary"));
          pages[i].classList.remove("hidden");
          tab.classList.add("text-primary");
        });
      });
    });
  </script>
  <style>
    .text-primary {
      color: #10b981;
    }
    .bg-primary {
      background-color: #10b981;
    }
  </style>
</head>
<body class="bg-gray-100 min-h-screen font-sans">
  <!-- Main Pages -->
  <div class="p-4 space-y-6">
    <!-- Home -->
    <div class="page" id="home">
      <h1 class="text-xl font-bold text-primary mb-4">Ringkasan Keuangan</h1>
      <div class="grid grid-cols-3 gap-4 text-center">
        <div class="bg-white p-4 rounded-xl shadow">
          <h2 class="text-sm">Pemasukan</h2>
          <p class="text-green-500 font-bold">Rp 2.000.000</p>
        </div>
        <div class="bg-white p-4 rounded-xl shadow">
          <h2 class="text-sm">Pengeluaran</h2>
          <p class="text-red-500 font-bold">Rp 750.000</p>
        </div>
        <div class="bg-white p-4 rounded-xl shadow">
          <h2 class="text-sm">Sisa</h2>
          <p class="text-blue-500 font-bold">Rp 1.250.000</p>
        </div>
      </div>
      <div class="mt-6">
        <h2 class="text-sm mb-2">Limit Bulanan</h2>
        <div class="w-full bg-gray-200 rounded-full h-3">
          <div class="bg-red-400 h-3 rounded-full" style="width: 75%;"></div>
        </div>
        <p class="text-sm mt-1">75% dari limit tercapai</p>
      </div>
      <button class="mt-6 w-full bg-primary text-white p-3 rounded-full shadow">+ Tambah Transaksi</button>
    </div>
    <!-- Transaksi -->
    <div class="page hidden" id="transaksi">
      <h1 class="text-xl font-bold text-primary mb-4">Riwayat Transaksi</h1>
      <ul class="space-y-2">
        <li class="bg-white p-3 rounded shadow flex justify-between">
          <span>Makan siang</span><span class="text-red-500">-Rp 25.000</span>
        </li>
        <li class="bg-white p-3 rounded shadow flex justify-between">
          <span>Uang saku</span><span class="text-green-500">+Rp 500.000</span>
        </li>
      </ul>
    </div>
    <!-- Notifikasi -->
    <div class="page hidden" id="notif">
      <h1 class="text-xl font-bold text-primary mb-4">Notifikasi</h1>
      <div class="bg-white p-4 rounded shadow">
        🎉 Kamu berhasil hemat minggu ini!
      </div>
    </div>
    <!-- Profil -->
    <div class="page hidden" id="profil">
      <h1 class="text-xl font-bold text-primary mb-4">Profil</h1>
      <div class="bg-white p-4 rounded shadow">
        <p><strong>Nama:</strong> Mahasiswa</p>
        <p><strong>Limit Bulanan:</strong> Rp 1.000.000</p>
        <button class="mt-4 bg-primary text-white px-4 py-2 rounded">Ubah Limit</button>
      </div>
    </div>
  </div>

  <!-- Bottom Nav -->
  <nav class="fixed bottom-0 left-0 right-0 bg-white border-t shadow-sm flex justify-around py-2 z-50">
    <button class="tab text-primary flex flex-col items-center">
      <i class="ri-home-4-line text-xl"></i>
      <span class="text-xs">Home</span>
    </button>
    <button class="tab flex flex-col items-center">
      <i class="ri-file-list-line text-xl"></i>
      <span class="text-xs">Transaksi</span>
    </button>
    <button class="tab flex flex-col items-center">
      <i class="ri-notification-3-line text-xl"></i>
      <span class="text-xs">Notifikasi</span>
    </button>
    <button class="tab flex flex-col items-center">
      <i class="ri-user-line text-xl"></i>
      <span class="text-xs">Profil</span>
    </button>
  </nav>

  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/remixicon/fonts/remixicon.css">
</body>
</html>
