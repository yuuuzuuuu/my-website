<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Catatan Uang Jajan Mahasiswa</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 font-sans">
  <div id="app" class="p-4 max-w-sm mx-auto">
    <!-- Dashboard -->
    <div id="dashboard">
      <h1 class="text-xl font-bold text-center mb-4">Catatan Uang Jajan</h1>
      <div class="bg-white rounded-xl shadow p-4">
        <p>Total Pemasukan: <span id="totalIncome" class="text-green-600 font-semibold">Rp 0</span></p>
        <p>Total Pengeluaran: <span id="totalExpense" class="text-red-500 font-semibold">Rp 0</span></p>
        <p class="font-bold mt-2">Sisa Uang: <span id="balance">Rp 0</span></p>
        <div class="mt-4">
          <p class="text-sm">Limit Pengeluaran: <span id="limitAmount">Rp 0</span></p>
          <div class="w-full bg-gray-200 rounded-full h-2.5 mt-1">
            <div id="limitBar" class="bg-red-400 h-2.5 rounded-full" style="width: 0%"></div>
          </div>
        </div>
      </div>
      <button onclick="showForm()" class="mt-6 w-full bg-green-500 hover:bg-green-600 text-white font-semibold py-2 rounded-xl">+ Tambah Transaksi</button>
    </div>
    <!-- Form Tambah Transaksi -->
    <div id="form" class="hidden">
      <h2 class="text-lg font-bold mb-4">Tambah Transaksi</h2>
      <form onsubmit="addTransaction(event)" class="bg-white p-4 rounded-xl shadow space-y-4">
        <select id="type" class="w-full p-2 border rounded-md">
          <option value="pemasukan">Pemasukan</option>
          <option value="pengeluaran">Pengeluaran</option>
        </select>
        <input type="number" id="amount" placeholder="Jumlah (Rp)" class="w-full p-2 border rounded-md" required />
        <input type="text" id="desc" placeholder="Deskripsi" class="w-full p-2 border rounded-md" />
        <input type="date" id="date" class="w-full p-2 border rounded-md" />
        <input type="text" id="cat" placeholder="Kategori (opsional)" class="w-full p-2 border rounded-md" />
        <button type="submit" class="w-full bg-primary hover:bg-green-600 text-white font-semibold py-2 rounded-xl">Simpan</button>
        <button type="button" onclick="hideForm()" class="w-full bg-gray-300 text-black py-2 rounded-xl">Batal</button>
      </form>
    </div>
  </div>

  <script>
    let transactions = JSON.parse(localStorage.getItem('transactions')) || [];
    let limit = 400000;
    document.getElementById("limitAmount").textContent = `Rp ${limit}`;

    function showForm() {
      document.getElementById("dashboard").classList.add("hidden");
      document.getElementById("form").classList.remove("hidden");
    }
    function hideForm() {
      document.getElementById("form").classList.add("hidden");
      document.getElementById("dashboard").classList.remove("hidden");
    }

    function addTransaction(e) {
      e.preventDefault();
      const type = document.getElementById("type").value;
      const amount = parseInt(document.getElementById("amount").value);
      const desc = document.getElementById("desc").value;
      const date = document.getElementById("date").value;
      const cat = document.getElementById("cat").value;
      transactions.push({ type, amount, desc, date, cat });
      localStorage.setItem('transactions', JSON.stringify(transactions));
      render();
      hideForm();
    }

    function render() {
      const income = transactions.filter(t => t.type === "pemasukan").reduce((sum, t) => sum + t.amount, 0);
      const expense = transactions.filter(t => t.type === "pengeluaran").reduce((sum, t) => sum + t.amount, 0);
      const balance = income - expense;
      const percent = Math.min((expense / limit) * 100, 100);

      document.getElementById("totalIncome").textContent = `Rp ${income}`;
      document.getElementById("totalExpense").textContent = `Rp ${expense}`;
      document.getElementById("balance").textContent = `Rp ${balance}`;
      document.getElementById("limitBar").style.width = `${percent}%`;
    }

    render();
  </script>
</body>
</html>
