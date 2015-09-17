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
		//tampilkan semua record tbl_barang
		$pencarian = "";
		$cari_data = "select * from tbl_barang order by kode_barang";
	}
	else //jika cari ada nilainya
	{
		$pencarian = $_REQUEST["cari"];
		//pencarian data berdasarkan kode / nama barang
		$cari_data = "select * from tbl_barang where kode_barang like '%$pencarian%' or nama_barang like '%$pencarian%' order by kode_barang";
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
        <td align="center" class="menu_utama">Halaman Data Barang</td>
      </tr>
      <tr>
        <td><table width="100%" border="0" cellspacing="0" cellpadding="3">
          <tr>
            <td width="75%"><form id="form1" name="form1" method="post" action="">
              Cari Data (Kode Nama) : 
              <input type="text" name="cari" id="cari" />
            </form></td>
            <td align="right"><a href="input_barang.php">Input Data Barang</a></td>
          </tr>
          <tr>
            <td colspan="2"><table width="100%" border="1" cellspacing="0" cellpadding="3">
              <tr>
                <th width="15%" align="center"><span class="isi_tabel">Kode Barang</span></th>
                <th width="30%" align="center"><span class="isi_tabel">Nama Barang</span></th>
                <th width="15%" align="center"><p><span class="isi_tabel">Satuan</span></p></th>
                <th width="15%" align="center"><span class="isi_tabel">Harga</span></th>
                <th width="10%" align="center"><span class="isi_tabel">Stock</span></th>
                <th width="15%" align="center"><span class="isi_tabel">Action</span></th>
              </tr>
              <?
			  	//mulainya perulangan
			  	//gunakan perulangan untuk menampilkan data
			  	while($data = mysql_fetch_array($hasil))
			  	{
				  	//tampilkan data barang
				  	$kode = $data[0];
				  	$nama = $data[1];
				  	$satuan = $data[2];
				  	$harga = $data[3];
				  	$stock = $data[4];
			  ?>
              <tr>
                <td><? echo $kode; ?></td>
                <td><? echo $nama; ?></td>
                <td><? echo $satuan; ?></td>
                <td><? echo $harga; ?></td>
                <td><? echo $stock; ?></td>
                <td align="center"><a href= "?data_barang.php&amp; kode=<? echo $kode; ?>&amp;act=hapus">Hapus</a></td>
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
<?
	//ambil nilai dari variabel link
	$kode = $_REQUEST["kode"];
	$act = $_REQUEST["act"];
	//jika act = hapus
	if ($act == "hapus")
	{
		//hapus record tbl_barang berdasarkan kode barang
		$hapus_data = "delete from tbl_barang where kode_barang = '$kode'";
		$hasil = mysql_query($hapus_data);
		//refresh halaman
		echo "<script> location.href='data_barang.php';</script>";
	}
?>
</body>
</html>
