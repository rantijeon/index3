
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Form Peminjaman Buku</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }
    input, select, textarea, button {
      display: block;
      margin: 10px 0;
      padding: 8px;
      width: 100%;
      max-width: 400px;
    }
    table {
      margin-top: 20px;
      width: 100%;
      border-collapse: collapse;
    }
    th, td {
      padding: 10px;
      border: 1px solid #ccc;
      text-align: left;
    }
    th {
      background-color: #f2f2f2;
    }
  </style>
</head>
<body>

  <h1>Form Peminjaman Buku</h1>

  <form id="formPeminjaman">
    <input type="text" id="nama" placeholder="Nama" required>
    <input type="text" id="nim" placeholder="NIM" required>
    <input type="date" id="tanggalPinjam" required>
    <input type="date" id="tanggalKembali" required>
    <input type="text" id="judulBuku" placeholder="Judul Buku" required>
    <select id="prodi" required>
      <option value="">Pilih Prodi</option>
      <option value="Teknik">Teknik</option>
      <option value="Ekonomo dan Bisnis">Ekonomi dan Bisnis</option>
      <option value="Ilmu Keperawatan">Ilmu keperawatan</option>
      <option value="Tarbiyah dan Keguruan">Tarbiyah dan Keguruan</option>
      <!-- Tambahkan prodi lain sesuai kebutuhan -->
    </select>
    <textarea id="keperluan" placeholder="Keperluan" rows="3" required></textarea>
    <button type="submit">Simpan</button>
  </form>

  <h2>Riwayat Peminjaman</h2>
  <table id="riwayatTable">
    <thead>
      <tr>
        <th>Nama</th>
        <th>NIM</th>
        <th>Tanggal Peminjaman</th>
        <th>Tanggal Pengembalian</th>
        <th>Judul Buku</th>
        <th>Prodi</th>
        <th>Keperluan</th>
      </tr>
    </thead>
    <tbody>
      <!-- Riwayat akan ditambahkan di sini -->
    </tbody>
  </table>

  <script>
    const form = document.getElementById('formPeminjaman');
    const tableBody = document.querySelector('#riwayatTable tbody');

    form.addEventListener('submit', function(event) {
      event.preventDefault();

      const nama = document.getElementById('nama').value;
      const nim = document.getElementById('nim').value;
      const tanggalPinjam = document.getElementById('tanggalPinjam').value;
      const tanggalKembali = document.getElementById('tanggalKembali').value;
      const judulBuku = document.getElementById('judulBuku').value;
      const prodi = document.getElementById('prodi').value;
      const keperluan = document.getElementById('keperluan').value;

      const row = document.createElement('tr');
      row.innerHTML = `
        <td>${nama}</td>
        <td>${nim}</td>
        <td>${tanggalPinjam}</td>
        <td>${tanggalKembali}</td>
        <td>${judulBuku}</td>
        <td>${prodi}</td>
        <td>${keperluan}</td>
      `;

      tableBody.appendChild(row);

      form.reset();
    });
  </script>

</body>
</html>
