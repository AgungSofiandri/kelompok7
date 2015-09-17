# kelompok7
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Sistem Informasi Penjualan - By : Wardoyo</title>
<link href="desain.css" rel="stylesheet" type="text/css" />
</head>

<body>
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
        <td align="center" class="menu_utama">Input Data Barang</td>
      </tr>
      <tr>
        <td><form id="form1" name="form1" method="post" action="simpan_barang.php">
          <table width="100%" border="1" cellspacing="0" cellpadding="3">
            <tr>
              <td width="40%">Kode Barang</td>
              <td width="4%">:</td>
              <td width="60%"><input name="kode" type="text" id="kode" size="15" maxlength="10" /></td>
            </tr>
            <tr>
              <td>Nama Barang</td>
              <td>:</td>
              <td><input name="nama" type="text" id="nama" size="35" maxlength="30" /></td>
            </tr>
            <tr>
              <td>Satuan</td>
              <td>:</td>
              <td><select name="satuan" size="1" id="satuan">
                <option value="Unit">Unit</option>
                <option value="Lusin">Lusin</option>
                <option value="Kotak">Kotak</option>
              </select></td>
            </tr>
            <tr>
              <td>Harga</td>
              <td>:</td>
              <td><input type="text" name="harga" id="harga" /></td>
            </tr>
            <tr>
              <td>Stock</td>
              <td>:</td>
              <td><input type="text" name="stock" id="stock" /></td>
            </tr>
            <tr>
              <td colspan="3" align="center"><input type="submit" name="proses" id="proses" value="Simpan" /> 
                <input type="reset" name="button2" id="button2" value="Reset" /></td>
              </tr>
          </table>
        </form></td>
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
