# kelompok7
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Sistem Informasi Penjualan - By : Wardoyo</title>
<link href="desain.css" rel="stylesheet" type="text/css" />
</head>

<body>
<?
	include "koneksi.php";
	//ambil nilai dari textfield "cari"
	$cari = $_REQUEST ["cari"];
	//jika cari = kosong
	if (empty($cari))
	{
		//tampilkan semua record tbl_penjualan
		$pencarian = "";
		$cari_data = "select * from tbl_penjualan order by no_faktur";
	}
	else //jika cari ada nilainya
	{
		$pencarian = $_REQUEST["cari"];
		//pencarian data berdasarkan kode / nama barang
		$cari_data = "select * from tbl_penjualan where no_faktur like '%$pencarian%' order by no_faktur";
	}
	//eksekusi perintah SQL
	$hasil = mysql_query($cari_data);
?>
<table width="100%" border="0" cellspacing="0" cellpadding="0">
  <tr>
    <td colspan="3">&nbsp;</td>
  </tr>
  <tr>
    <td width="20%" height="500" valign="top" class="garis_utama"><table width="100%" border="0" cellspacing="0" cellpadding="3">
      <tr>
        <td align="center" class="menu_utama">Menu Utama</td>
      </tr>
      <tr>
        <td align="center" class="isi_menu"><a href="index.php">Beranda</a></td>
      </tr>
      <tr>
        <td align="center" class="isi_menu"><a href="data_barang.php">Data Barang</a></td>
      </tr>
      <tr>
        <td align="center" class="isi_menu"><a href="data_penjualan.php">Data Penjualan</a></td>
      </tr>
      <tr>
        <td align="center" class="isi_menu"><a href="laporan.php">Laporan</a></td>
      </tr>
    </table></td>
    <td width="60%" valign="top"><table width="100%" border="0" cellspacing="0" cellpadding="3">
      <tr>
        <td align="center" class="menu_utama">Halaman Data Penjualan</td>
      </tr>
      <tr>
        <td><table width="100%" border="0" cellspacing="0" cellpadding="3">
          <tr>
            <td width="75%"><form id="form1" name="form1" method="post" action="">
              Cari Data (Kode Nama) :
              <input type="text" name="cari" id="cari" />
            </form></td>
            <td align="right"><a href="input_penjualan.php">Input Penjualan</a></td>
          </tr>
          <tr>
            <td colspan="2"><table width="100%" border="1" cellspacing="0" cellpadding="3">
              <tr>
                <th width="15%" align="center"><span class="isi_tabel">No Faktur</span></th>
                <th width="20%" align="center"><span class="isi_tabel">Tanggal</span></th>
                <th width="15%" align="center"><p><span class="isi_tabel">Kode Barang</span></p></th>
                <th width="15%" align="center"><span class="isi_tabel">Qty</span></th>
                <th width="20%" align="center"><span class="isi_tabel">Total Harga</span></th>
                <th width="15%" align="center"><span class="isi_tabel">Action</span></th>
              </tr>
              <?
			  	//mulainya perulangan
			  	//gunakan perulangan untuk menampilkan data
			  	while($data = mysql_fetch_array($hasil))
			  	{
				  	//tampilkan data penjualan
				  	$no_faktur = $data[0];
				  	$tgl_faktur = $data[1];
				  	$kode_barang = $data[2];
				  	$qty = $data[3];
				  	$total_harga = $data[4];
			  ?>
              <tr>
                <td><? echo $no_faktur; ?></td>
                <td><? echo $tgl_faktur; ?></td>
                <td><? echo $kode_barang; ?></td>
                <td><? echo $qty; ?></td>
                <td><? echo $total_harga; ?></td>
                <td align="center"><a href= "?data_penjualan.php&amp; no_faktur=<? echo $no_faktur; ?>&amp;act=hapus">Hapus</a></td>
              </tr>
              <?
			  	//akhir perulangan
			  	}
			  ?>
            </table></td>
          </tr>
        </table></td>
      </tr>
    </table></td>
    <td width="20%" valign="top" class="garis_utama"><table width="100%" border="0" cellspacing="0" cellpadding="3">
      <tr>
        <td class="menu_utama">Link Halaman</td>
      </tr>
      <tr>
        <td class="isi_menu"><a href="http://www.google.com" target="_blank">Google</a></td>
      </tr>
      <tr>
        <td class="isi_menu"><a href="http://www.yahoo.com" target="_blank">Yahoo</a></td>
      </tr>
      <tr>
        <td class="isi_menu"><a href="http://www.facebook.com" target="_blank">Facebook</a></td>
      </tr>
      <tr>
        <td class="isi_menu"><a href="http://www.twitter.com" target="_blank">Twitter</a></td>
      </tr>
    </table></td>
  </tr>
  <tr>
    <td colspan="3" align="center" class="garis_footer">
      Copy Right (C) 2015 - By : Kelompok7</td>
  </tr>
</table>
</body>
</html>
