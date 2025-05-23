<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <title>ZhIndonesianbirdfarm</title>
  <style>
    body { font-family: sans-serif; padding: 20px; background: #f0fdf4; }
    h2 { margin-top: 0; }
    input, select, textarea { width: 100%; margin-bottom: 8px; padding: 5px; }
    button { padding: 6px 12px; }
    table { width: 100%; border-collapse: collapse; margin-top: 20px; }
    th, td { border: 1px solid #ccc; padding: 8px; text-align: center; }
  </style>
</head>
<body>

  <h2>Tambah / Edit Data Burung</h2>
  <form id="formBurung">
    <input type="text" id="nama" placeholder="Nama Burung" required />
    <select id="jenis">
      <option value="Jantan">Jantan</option>
      <option value="Betina">Betina</option>
    </select>
    <input type="number" id="umur" placeholder="Umur (bulan)" />
    <input type="date" id="tanggal" />
    <input type="text" id="asal" placeholder="Asal" />
    <textarea id="catatan" placeholder="Catatan"></textarea>
    <button type="submit">Simpan</button>
  </form>

  <h2>Daftar Burung</h2>
  <table id="tabelBurung">
    <thead>
      <tr><th>No</th><th>Nama</th><th>JK</th><th>Umur</th><th>Tanggal</th><th>Asal</th><th>Aksi</th></tr>
    </thead>
    <tbody></tbody>
  </table>

  <script>
    let daftar = [];
    let editIndex = null;

    document.getElementById("formBurung").onsubmit = function(e) {
      e.preventDefault();
      const data = {
        nama: document.getElementById("nama").value,
        jenis: document.getElementById("jenis").value,
        umur: document.getElementById("umur").value,
        tanggal: document.getElementById("tanggal").value,
        asal: document.getElementById("asal").value,
        catatan: document.getElementById("catatan").value,
      };

      if (editIndex !== null) {
        daftar[editIndex] = data;
        editIndex = null;
      } else {
        daftar.push(data);
      }

      this.reset();
      tampilkan();
    };

    function tampilkan() {
      const tbody = document.querySelector("#tabelBurung tbody");
      tbody.innerHTML = "";
      daftar.forEach((b, i) => {
        const row = `<tr>
          <td>${i+1}</td>
          <td>${b.nama}</td>
          <td>${b.jenis}</td>
          <td>${b.umur}</td>
          <td>${b.tanggal}</td>
          <td>${b.asal}</td>
          <td>
            <button onclick="edit(${i})">Edit</button>
            <button onclick="hapus(${i})">Hapus</button>
          </td>
        </tr>`;
        tbody.innerHTML += row;
      });
    }

    function edit(i) {
      const b = daftar[i];
      document.getElementById("nama").value = b.nama;
      document.getElementById("jenis").value = b.jenis;
      document.getElementById("umur").value = b.umur;
      document.getElementById("tanggal").value = b.tanggal;
      document.getElementById("asal").value = b.asal;
      document.getElementById("catatan").value = b.catatan;
      editIndex = i;
    }

    function hapus(i) {
      if (confirm("Yakin mau hapus data ini?")) {
        daftar.splice(i, 1);
        tampilkan();
      }
    }
  </script>

</body>
</html><!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <title>ZhIndonesianbirdfarm</title>
  <style>
    body { font-family: sans-serif; padding: 20px; background: #f0fdf4; }
    h2 { margin-top: 0; }
    input, select, textarea { width: 100%; margin-bottom: 8px; padding: 5px; }
    button { padding: 6px 12px; }
    table { width: 100%; border-collapse: collapse; margin-top: 20px; }
    th, td { border: 1px solid #ccc; padding: 8px; text-align: center; }
  </style>
</head>
<body>

  <h2>Tambah / Edit Data Burung</h2>
  <form id="formBurung">
    <input type="text" id="nama" placeholder="Nama Burung" required />
    <select id="jenis">
      <option value="Jantan">Jantan</option>
      <option value="Betina">Betina</option>
    </select>
    <input type="number" id="umur" placeholder="Umur (bulan)" />
    <input type="date" id="tanggal" />
    <input type="text" id="asal" placeholder="Asal" />
    <textarea id="catatan" placeholder="Catatan"></textarea>
    <button type="submit">Simpan</button>
  </form>

  <h2>Daftar Burung</h2>
  <table id="tabelBurung">
    <thead>
      <tr><th>No</th><th>Nama</th><th>JK</th><th>Umur</th><th>Tanggal</th><th>Asal</th><th>Aksi</th></tr>
    </thead>
    <tbody></tbody>
  </table>

  <script>
    let daftar = [];
    let editIndex = null;

    document.getElementById("formBurung").onsubmit = function(e) {
      e.preventDefault();
      const data = {
        nama: document.getElementById("nama").value,
        jenis: document.getElementById("jenis").value,
        umur: document.getElementById("umur").value,
        tanggal: document.getElementById("tanggal").value,
        asal: document.getElementById("asal").value,
        catatan: document.getElementById("catatan").value,
      };

      if (editIndex !== null) {
        daftar[editIndex] = data;
        editIndex = null;
      } else {
        daftar.push(data);
      }

      this.reset();
      tampilkan();
    };

    function tampilkan() {
      const tbody = document.querySelector("#tabelBurung tbody");
      tbody.innerHTML = "";
      daftar.forEach((b, i) => {
        const row = `<tr>
          <td>${i+1}</td>
          <td>${b.nama}</td>
          <td>${b.jenis}</td>
          <td>${b.umur}</td>
          <td>${b.tanggal}</td>
          <td>${b.asal}</td>
          <td>
            <button onclick="edit(${i})">Edit</button>
            <button onclick="hapus(${i})">Hapus</button>
          </td>
        </tr>`;
        tbody.innerHTML += row;
      });
    }

    function edit(i) {
      const b = daftar[i];
      document.getElementById("nama").value = b.nama;
      document.getElementById("jenis").value = b.jenis;
      document.getElementById("umur").value = b.umur;
      document.getElementById("tanggal").value = b.tanggal;
      document.getElementById("asal").value = b.asal;
      document.getElementById("catatan").value = b.catatan;
      editIndex = i;
    }

    function hapus(i) {
      if (confirm("Yakin mau hapus data ini?")) {
        daftar.splice(i, 1);
        tampilkan();
      }
    }
  </script>

</body>
</html>
